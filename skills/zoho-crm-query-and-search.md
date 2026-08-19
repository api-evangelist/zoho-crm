---
name: Query and search Zoho CRM with COQL
description: Retrieve Zoho CRM records by criteria using COQL, module search and record counts, instead of paging whole modules and filtering client-side.
api: openapi/zoho-crm-coql-openapi.json, openapi/zoho-crm-module-search-openapi.json, openapi/zoho-crm-record-count-openapi.json
operations: [executeCOQLQuery, searchRecords, getCount]
---

# Query and search Zoho CRM

Paging a whole module to filter locally burns API credits fast — most calls cost 1 credit
against a rolling 24-hour budget. Query server-side.

## Preconditions

- `Authorization: Zoho-oauthtoken {access_token}`.
- Scopes: `ZohoCRM.coql.READ` + `ZohoCRM.modules.READ` for COQL;
  `ZohoCRM.modules.{Module}.READ` + `ZohoSearch.securesearch.READ` for search and count.

## Steps

1. **Count first** — `getCount` `GET /{moduleApiName}/actions/count` to size the result
   before deciding between a query and a bulk job.
2. **Structured query** — `executeCOQLQuery` `POST /coql` with a `select_query` string.
   COQL is Zoho's SQL-like language over CRM records; it returns the same `{data, info}`
   envelope as the record APIs.
3. **Keyword / field search** — `searchRecords` `GET /{module}/search` with `criteria`,
   `email`, `phone` or `word`.
4. **Escalate to bulk** — if the result set is large, stop paging and use the Bulk Read job
   flow instead (see the *Export and import in bulk* skill).

## Rules

- Field names in COQL must be real field `api_name` values from `getFields`.
- `info.more_records` still governs pagination on COQL results.
- COQL and search read live data only; deleted records come from `getDeletedRecords`.

See `conventions/zoho-crm-conventions.yml`.
