---
name: Create and update Zoho CRM records without creating duplicates
description: Write records to any Zoho CRM module with retry-safe semantics, handling the 207 Multi-Status partial-success envelope and the absence of an idempotency key.
api: openapi/zoho-crm-record-openapi.json
operations: [createRecords, upsertRecords, getRecords, getRecord, updateRecord, updateRecords, deleteRecord, getDeletedRecords, cloneRecord]
---

# Create and update Zoho CRM records safely

Zoho CRM publishes **no idempotency key**. There is no `Idempotency-Key` header, no
client-supplied request id, and no dedupe token anywhere in the 105 published specs. A
retried `createRecords` will create a second record.

## Preconditions

- `Authorization: Zoho-oauthtoken {access_token}`.
- Module API name and field API names resolved first — see the
  *Discover Zoho CRM modules and fields* skill.
- Scopes: `ZohoCRM.modules.{Module}.CREATE` / `.READ` / `.UPDATE` / `.DELETE`.

## Steps

1. **Read** — `getRecords` `GET /{module}` with `fields=` (mandatory, max 50),
   `per_page` (max 200), `sort_by` (`id` | `Created_Time` | `Modified_Time`) and
   `sort_order`. Read a single record with `getRecord` `GET /{module}/{recordID}`.
2. **Page** — follow `info.more_records`. Past 2000 records `page` stops working; switch to
   `page_token` from `info.next_page_token` (user-specific, 24-hour expiry, cannot be
   combined with `page`).
3. **Write, retry-safely** — prefer `upsertRecords` `POST /{module}/upsert` with
   `duplicate_check_fields` over `createRecords`. Upsert converges on one record when
   retried; create does not.
4. **Check every element** — a `207 Multi-Status` means the batch partially succeeded.
   Iterate `data[]` and read each element's own `code`/`status`/`message`. A `2xx` alone is
   not success.
5. **Update** — `updateRecord` `PUT /{module}/{recordID}` (single) or `updateRecords`
   `PUT /{module}` (batch). Both are idempotent in Zoho's own description.
6. **Handle concurrency** — send `If-Modified-Since` on updates. `412` means the record
   changed underneath you: re-read, re-apply, retry. `304` means nothing changed.
7. **Delete / recover** — `deleteRecord`, and `getDeletedRecords` `GET /{module}/deleted`
   to enumerate what was removed.

## Rules

- Retry-safe: `upsertRecords`, `updateRecord`, `updateRecords`.
- **Not** retry-safe: `createRecords`, `cloneRecord`.
- `429` means either the 24-hour credit budget or the org concurrency limit is exhausted;
  the status does not tell you which, and no `Retry-After` is returned. Watch
  `X-API-CREDITS-REMAINING`, which only appears once you are past 50% of the budget.

See `errors/zoho-crm-problem-types.yml` and `rate-limits/zoho-crm-rate-limits.yml`.
