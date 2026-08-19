---
name: Discover Zoho CRM modules and fields before writing
description: Resolve the tenant's real module API names and field definitions before constructing any Zoho CRM record body, because Zoho CRM's schema is per-org runtime data, not a fixed contract.
api: openapi/zoho-crm-modules-openapi.json, openapi/zoho-crm-fields-openapi.json
operations: [getModules, getModuleByApiName, getFields, getFieldsWithID]
---

# Discover Zoho CRM modules and fields

Zoho CRM's record APIs are templated on `{module}`. There is no static list of business
objects in the contract — the modules an org has, their API names, and the fields on each
one are all per-tenant runtime data. Skipping this step is the number one cause of
`INVALID_DATA` on a first write.

## Preconditions

- OAuth 2.0 access token from `https://accounts.zoho.com/oauth/v2/token`.
- Header: `Authorization: Zoho-oauthtoken {access_token}` — **not** `Bearer`.
- Base URL: `https://zohoapis.{dc}/crm/v8` where `dc` ∈ `com | eu | in | cn | au`. Resolve
  the org's data centre first; the same account is not reachable on every host.
- Scopes: `ZohoCRM.settings.modules.READ`, `ZohoCRM.settings.fields.READ`.

## Steps

1. `getModules` — `GET /settings/modules`. Read `api_name` for every module the org has.
   Custom modules appear here with their real API names; do not assume `Leads`/`Deals`.
2. `getModuleByApiName` — `GET /settings/modules/{moduleIdentifier}` for the module you
   intend to write to, to confirm which operations it supports.
3. `getFields` — `GET /settings/fields?module={api_name}`. This is the authoritative field
   list: `api_name`, `data_type`, `mandatory`, and pick-list values.
4. Build the record body from step 3's `api_name` values only. Any key not in that list is
   rejected.
5. Substitute the module API name into every subsequent scope request:
   `ZohoCRM.modules.Leads.READ`, never `ZohoCRM.modules.{module_API_name}.READ`.

## Rules

- `fields` is mandatory on list reads and caps at 50 field API names.
- A `403` here almost always means scope mismatch, not a permission problem — re-check the
  scope on the operation in the OAS file.

See `conventions/zoho-crm-conventions.yml` and `scopes/zoho-crm-scopes.yml`.
