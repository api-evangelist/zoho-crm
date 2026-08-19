---
name: Convert a Zoho CRM lead into an account, contact and deal
description: Run the lead-conversion flow, the one Zoho CRM write that is neither idempotent nor cheap, with the right preconditions.
api: openapi/zoho-crm-convert-openapi.json, openapi/zoho-crm-conversion-option-openapi.json
operations: [convertLead, getLeadConversionOptions, getRecord]
---

# Convert a Zoho CRM lead

Conversion turns one Lead into an Account, a Contact and optionally a Deal. It costs
**5 API credits**, it is **not idempotent**, and it cannot be undone through the API.

## Preconditions

- `Authorization: Zoho-oauthtoken {access_token}`.
- Scope: `ZohoCRM.modules.leads.CREATE`.
- The lead must exist and must not already be converted.

## Steps

1. `getRecord` — `GET /Leads/{recordID}`. Confirm the lead is real and unconverted before
   spending the call.
2. `getLeadConversionOptions` — read the conversion options the org has configured
   (`openapi/zoho-crm-conversion-option-openapi.json`) so you supply the fields it expects.
3. `convertLead` — `POST /Leads/{leadId}/actions/convert` with the assignment, deal and
   carry-over-tags options.
4. Read the response ids for the created Account, Contact and Deal and store them.

## Rules

- **Never retry blindly.** A failed-looking `convertLead` may have succeeded server-side. On
  an ambiguous failure, re-read the lead first — if it is now converted, stop.
- Mass conversion has its own operation (`openapi/zoho-crm-mass-convert-openapi.json`); do
  not loop `convertLead`.

See `conventions/zoho-crm-conventions.yml` for the retry-safety table.
