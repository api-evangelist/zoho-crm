---
name: Export and import Zoho CRM data in bulk
description: Move large volumes in and out of Zoho CRM with the asynchronous Bulk Read and Bulk Write job APIs instead of paging the record endpoints.
api: openapi/zoho-crm-bulk-read-openapi.json, openapi/zoho-crm-bulk-write-openapi.json, openapi/zoho-crm-upload-openapi.json
operations: [createBulkReadJob, getBulkReadJobDetails, downloadResult, createBulkWriteJob, getJobDetails]
---

# Export and import Zoho CRM data in bulk

Bulk Read and Bulk Write are **asynchronous jobs**, not request/response calls. You create a
job, poll it, then download or reconcile the result.

## Preconditions

- `Authorization: Zoho-oauthtoken {access_token}`.
- Scopes: `ZohoCRM.bulk.READ` + `ZohoCRM.modules.ALL` to export; `ZohoCRM.bulk.CREATE` to import.
- Budget: **Bulk Write Initialize costs 500 API credits per call.** Do not use it as a retry
  loop.

## Steps — export

1. `createBulkReadJob` — `POST /read` with the module and an optional COQL-style criteria
   block. Returns a job id.
2. `getBulkReadJobDetails` — `GET /read/{jobId}`. Poll until the job state is complete.
3. `downloadResult` — `GET /read/{jobId}/result`. Returns the result archive.

## Steps — import

1. Upload the source file to Zoho's file store (see `openapi/zoho-crm-upload-openapi.json`).
2. `createBulkWriteJob` — `POST /write` referencing the uploaded file and the target module
   and field mapping.
3. `getJobDetails` — `GET /write/{jobId}`. Poll until complete, then read the per-record
   result file: a completed job can still contain failed rows.

## Rules

- Poll with backoff. There is no webhook for job completion.
- A completed job is not a successful job — always read the result file.
- Concurrency limits (5–25 simultaneous calls depending on edition) apply to the polling
  loop too.

See `rate-limits/zoho-crm-rate-limits.yml`.
