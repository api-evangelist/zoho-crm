# Zoho CRM

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Zoho CRM is Zoho Corporation's AI-powered sales and customer relationship management platform, used to manage leads, contacts, accounts, deals, activities and customer engagement across channels. Its REST API is currently at v8 and is published as first-party OpenAPI 3.1.0 — 105 specification files covering 405 operations, hosted by Zoho at github.com/zoho/crm-oas and linked from the developer documentation. Authentication is OAuth 2.0 authorization-code against accounts.zoho.com with 458 distinct scopes, and every specification templates both the data centre and the API version into the server URL (https://zohoapis.{dc}/crm/{version}, dc one of com, eu, in, cn, au). Usage is metered in API credits on a rolling 24-hour window rather than in requests, alongside an org-level concurrency cap. Zoho additionally ships server-side SDKs for Node.js, TypeScript, Python, PHP, C#, Java, Ruby and Scala, a widget/extension CLI (ZET), a documented webhook surface (Instant Notifications), and a hosted MCP product that names Zoho CRM as a supported app.

**Areas:** CRM · Sales · Marketing Automation · Lead Management · Customer Engagement · Sales Automation · Contact Management · Pipeline Management · Software-as-a-Service · OpenAPI · Authentication

## Zoho CRM on APIs.io

Everything profiled for Zoho CRM is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/zoho-crm/](https://apis.io/providers/zoho-crm/)** — or go straight to one of the APIs or properties below.

### APIs (36)

- [Zoho CRM Actions API](https://apis.io/apis/zoho-crm/zoho-crm-actions-api/) — The Actions API from Zoho CRM — 36 operation(s) for actions.
- [Zoho CRM Appointments S API](https://apis.io/apis/zoho-crm/zoho-crm-appointments-s-api/) — The Appointments S API from Zoho CRM — 2 operation(s) for appointments s.
- [Zoho CRM Attachments API](https://apis.io/apis/zoho-crm/zoho-crm-attachments-api/) — The Attachments API from Zoho CRM — 2 operation(s) for attachments.
- [Zoho CRM Composite Requests API](https://apis.io/apis/zoho-crm/zoho-crm-composite-requests-api/) — The Composite Requests API from Zoho CRM — 1 operation(s) for composite requests.
- [Zoho CRM Contact Roles API](https://apis.io/apis/zoho-crm/zoho-crm-contact-roles-api/) — The Contact Roles API from Zoho CRM — 2 operation(s) for contact roles.
- [Zoho CRM Contacts API](https://apis.io/apis/zoho-crm/zoho-crm-contacts-api/) — The Contacts API from Zoho CRM — 4 operation(s) for contacts.
- [Zoho CRM Coql API](https://apis.io/apis/zoho-crm/zoho-crm-coql-api/) — The Coql API from Zoho CRM — 1 operation(s) for coql.
- [Zoho CRM Deleted API](https://apis.io/apis/zoho-crm/zoho-crm-deleted-api/) — The Deleted API from Zoho CRM — 2 operation(s) for deleted.
- [Zoho CRM Email Drafts API](https://apis.io/apis/zoho-crm/zoho-crm-email-drafts-api/) — The Email Drafts API from Zoho CRM — 2 operation(s) for email drafts.
- [Zoho CRM Emails API](https://apis.io/apis/zoho-crm/zoho-crm-emails-api/) — The Emails API from Zoho CRM — 2 operation(s) for emails.
- [Zoho CRM Emails Sharing Details API](https://apis.io/apis/zoho-crm/zoho-crm-emails-sharing-details-api/) — The Emails Sharing Details API from Zoho CRM — 1 operation(s) for emails sharing details.
- [Zoho CRM Events API](https://apis.io/apis/zoho-crm/zoho-crm-events-api/) — The Events API from Zoho CRM — 1 operation(s) for events.
- [Zoho CRM Features API](https://apis.io/apis/zoho-crm/zoho-crm-features-api/) — The Features API from Zoho CRM — 2 operation(s) for features.
- [Zoho CRM Files API](https://apis.io/apis/zoho-crm/zoho-crm-files-api/) — The Files API from Zoho CRM — 1 operation(s) for files.
- [Zoho CRM Global Picklists API](https://apis.io/apis/zoho-crm/zoho-crm-global-picklists-api/) — The Global Picklists API from Zoho CRM — 3 operation(s) for global picklists.
- [Zoho CRM Holidays API](https://apis.io/apis/zoho-crm/zoho-crm-holidays-api/) — Operations for managing holidays that affect business hours and shift schedules
- [Zoho CRM Layouts API](https://apis.io/apis/zoho-crm/zoho-crm-layouts-api/) — The Layouts API from Zoho CRM — 1 operation(s) for layouts.
- [Zoho CRM Leads API](https://apis.io/apis/zoho-crm/zoho-crm-leads-api/) — The Leads API from Zoho CRM — 3 operation(s) for leads.
- [Zoho CRM Locking Information S API](https://apis.io/apis/zoho-crm/zoho-crm-locking-information-s-api/) — The Locking Information S API from Zoho CRM — 2 operation(s) for locking information s.
- [Zoho CRM Notes API](https://apis.io/apis/zoho-crm/zoho-crm-notes-api/) — The Notes API from Zoho CRM — 4 operation(s) for notes.
- [Zoho CRM Org API](https://apis.io/apis/zoho-crm/zoho-crm-org-api/) — The Org API from Zoho CRM — 5 operation(s) for org.
- [Zoho CRM Photo API](https://apis.io/apis/zoho-crm/zoho-crm-photo-api/) — The Photo API from Zoho CRM — 1 operation(s) for photo.
- [Zoho CRM Read API](https://apis.io/apis/zoho-crm/zoho-crm-read-api/) — The Read API from Zoho CRM — 3 operation(s) for read.
- [Zoho CRM Records API](https://apis.io/apis/zoho-crm/zoho-crm-records-api/) — The Records API from Zoho CRM — 3 operation(s) for records.
- [Zoho CRM Search API](https://apis.io/apis/zoho-crm/zoho-crm-search-api/) — The Search API from Zoho CRM — 1 operation(s) for search.
- [Zoho CRM Services S API](https://apis.io/apis/zoho-crm/zoho-crm-services-s-api/) — The Services S API from Zoho CRM — 2 operation(s) for services s.
- [Zoho CRM Settings API](https://apis.io/apis/zoho-crm/zoho-crm-settings-api/) — The Settings API from Zoho CRM — 107 operation(s) for settings.
- [Zoho CRM Timeline API](https://apis.io/apis/zoho-crm/zoho-crm-timeline-api/) — The Timeline API from Zoho CRM — 1 operation(s) for timeline.
- [Zoho CRM Upload API](https://apis.io/apis/zoho-crm/zoho-crm-upload-api/) — The Upload API from Zoho CRM — 1 operation(s) for upload.
- [Zoho CRM Upsert API](https://apis.io/apis/zoho-crm/zoho-crm-upsert-api/) — The Upsert API from Zoho CRM — 1 operation(s) for upsert.
- [Zoho CRM Users API](https://apis.io/apis/zoho-crm/zoho-crm-users-api/) — The Users API from Zoho CRM — 10 operation(s) for users.
- [Zoho CRM Workflow Configurations API](https://apis.io/apis/zoho-crm/zoho-crm-workflow-configurations-api/) — The Workflow Configurations API from Zoho CRM — 1 operation(s) for workflow configurations.
- [Zoho CRM Write API](https://apis.io/apis/zoho-crm/zoho-crm-write-api/) — The Write API from Zoho CRM — 2 operation(s) for write.
- [Zoho CRM Zia Org Enrichment API](https://apis.io/apis/zoho-crm/zoho-crm-zia-org-enrichment-api/) — The Zia Org Enrichment API from Zoho CRM — 2 operation(s) for zia org enrichment.
- [Zoho CRM Zoho CRM Related Records API](https://apis.io/apis/zoho-crm/zoho-crm-zoho-crm-related-records-api-api/) — The Zoho CRM Related Records API API from Zoho CRM — 2 operation(s) for zoho crm related records api.
- [Zoho CRM APIS API](https://apis.io/apis/zoho-crm/zoho-crm-apis-api/) — The Apis API from Zoho CRM — 1 operation(s) for apis.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Zoho CRM Notifications API](https://apis.io/asyncapis/zoho-crm/zoho-crm-notifications-asyncapi/)

#### Event channels (20)

Individual events and webhooks the provider emits.

- [Accounts](https://apis.io/channels/zoho-crm/accounts/)
- [Appointments](https://apis.io/channels/zoho-crm/appointments/)
- [Calls](https://apis.io/channels/zoho-crm/calls/)
- [Campaigns](https://apis.io/channels/zoho-crm/campaigns/)
- [Cases](https://apis.io/channels/zoho-crm/cases/)
- [Contacts](https://apis.io/channels/zoho-crm/contacts/)
- [Custom](https://apis.io/channels/zoho-crm/custom/)
- [Deals](https://apis.io/channels/zoho-crm/deals/)
- [Invoices](https://apis.io/channels/zoho-crm/invoices/)
- [Leads](https://apis.io/channels/zoho-crm/leads/)
- [Meetings](https://apis.io/channels/zoho-crm/meetings/)
- [Price_Books](https://apis.io/channels/zoho-crm/price-books/)
- [Products](https://apis.io/channels/zoho-crm/products/)
- [Purchase_Orders](https://apis.io/channels/zoho-crm/purchase-orders/)
- [Quotes](https://apis.io/channels/zoho-crm/quotes/)
- [Sales_Orders](https://apis.io/channels/zoho-crm/sales-orders/)
- [Services](https://apis.io/channels/zoho-crm/services/)
- [Solutions](https://apis.io/channels/zoho-crm/solutions/)
- [Tasks](https://apis.io/channels/zoho-crm/tasks/)
- [Vendors](https://apis.io/channels/zoho-crm/vendors/)

#### GraphQL (1)

GraphQL schemas.

- [Moved to /providers/zoho-crm/](https://apis.io/graphqls/zoho-crm/zoho-crm-graphql/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Zoho MCP](https://apis.io/servers/zoho-crm/zoho-mcp/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Zoho Crm Agentic Access](https://apis.io/agentic-access/zoho-crm/zoho-crm-agentic-access/)

#### JSON Schema (48)

The data models the API reads and writes.

- [ActionResponse](https://apis.io/schemas/zoho-crm/zoho-crm-action-response/)
- [ApiName](https://apis.io/schemas/zoho-crm/zoho-crm-api-name/)
- [AttachmentListResponse](https://apis.io/schemas/zoho-crm/zoho-crm-attachment-list-response/)
- [AttachmentSuccessResponse](https://apis.io/schemas/zoho-crm/zoho-crm-attachment-success-response/)
- [BulkOperationResponse](https://apis.io/schemas/zoho-crm/zoho-crm-bulk-operation-response/)
- [ConversionRequestWrapper](https://apis.io/schemas/zoho-crm/zoho-crm-conversion-request-wrapper/)
- [ConversionScheduledWrapper](https://apis.io/schemas/zoho-crm/zoho-crm-conversion-scheduled-wrapper/)
- [ConversionSuccessWrapper](https://apis.io/schemas/zoho-crm/zoho-crm-conversion-success-wrapper/)
- [CoqlFieldSchema](https://apis.io/schemas/zoho-crm/zoho-crm-coql-field-schema/)
- [DataError](https://apis.io/schemas/zoho-crm/zoho-crm-data-error/)
- [DeleteRelationsSuccessResponse](https://apis.io/schemas/zoho-crm/zoho-crm-delete-relations-success-response/)
- [Delete207SuccessResponse](https://apis.io/schemas/zoho-crm/zoho-crm-delete207-success-response/)
- [Error Response Core](https://apis.io/schemas/zoho-crm/zoho-crm-error-response-core1168955151/)
- [Error Response Core](https://apis.io/schemas/zoho-crm/zoho-crm-error-response-core1544688711/)
- [Error Response Core](https://apis.io/schemas/zoho-crm/zoho-crm-error-response-core2137699283/)
- [Error Response Core](https://apis.io/schemas/zoho-crm/zoho-crm-error-response-core297287888/)
- [FieldLabel](https://apis.io/schemas/zoho-crm/zoho-crm-field-label/)
- [FieldRequestBodySchema](https://apis.io/schemas/zoho-crm/zoho-crm-field-request-body-schema/)
- [FieldSchema](https://apis.io/schemas/zoho-crm/zoho-crm-field-schema/)
- [FieldUpdateRequestBodySchema](https://apis.io/schemas/zoho-crm/zoho-crm-field-update-request-body-schema/)
- [GetservicessResponse200](https://apis.io/schemas/zoho-crm/zoho-crm-getservicess-response200/)
- [GetworkflowconfigurationsResponse200](https://apis.io/schemas/zoho-crm/zoho-crm-getworkflowconfigurations-response200/)
- [HolidaysSuccessResponse](https://apis.io/schemas/zoho-crm/zoho-crm-holidays-success-response/)
- [Id](https://apis.io/schemas/zoho-crm/zoho-crm-id/)
- [Info](https://apis.io/schemas/zoho-crm/zoho-crm-info/)
- …and 23 more published on APIs.io

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Zoho Crm Context](https://apis.io/jsonld/zoho-crm/zoho-crm-context/)

#### Overlays (141)

OpenAPI overlays, including conversational phrasing for each operation.

- [Zoho Crm Actions Api Phrasing Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-actions-api-phrasing-overlay/)
- [Zoho Crm Apis Api Phrasing Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-apis-api-phrasing-overlay/)
- [Zoho Crm Apis Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-apis-overlay/)
- [Zoho Crm Appointment Preference Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-appointment-preference-overlay/)
- [Zoho Crm Appointments Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-appointments-overlay/)
- [Zoho Crm Appointments S Api Phrasing Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-appointments-s-api-phrasing-overlay/)
- [Zoho Crm Assignment Rules Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-assignment-rules-overlay/)
- [Zoho Crm Associate Email Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-associate-email-overlay/)
- [Zoho Crm Attachments Api Phrasing Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-attachments-api-phrasing-overlay/)
- [Zoho Crm Attachments Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-attachments-overlay/)
- [Zoho Crm Audit Log Export Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-audit-log-export-overlay/)
- [Zoho Crm Available Currencies Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-available-currencies-overlay/)
- [Zoho Crm Bulk Read Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-bulk-read-overlay/)
- [Zoho Crm Bulk Write Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-bulk-write-overlay/)
- [Zoho Crm Business Hours Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-business-hours-overlay/)
- [Zoho Crm Cadences Execution Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-cadences-execution-overlay/)
- [Zoho Crm Cadences Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-cadences-overlay/)
- [Zoho Crm Call Preferences Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-call-preferences-overlay/)
- [Zoho Crm Cancel Meetings Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-cancel-meetings-overlay/)
- [Zoho Crm Change Owner Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-change-owner-overlay/)
- [Zoho Crm Composite Requests Api Phrasing Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-composite-requests-api-phrasing-overlay/)
- [Zoho Crm Composite Requests Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-composite-requests-overlay/)
- [Zoho Crm Contact Roles Api Phrasing Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-contact-roles-api-phrasing-overlay/)
- [Zoho Crm Contact Roles Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-contact-roles-overlay/)
- [Zoho Crm Contacts Api Phrasing Overlay](https://apis.io/overlays/zoho-crm/zoho-crm-contacts-api-phrasing-overlay/)
- …and 116 more published on APIs.io

#### Governance rules (2)

Spectral rulesets for the provider's contracts.

- [Zoho CRM — asyncapi rules](https://apis.io/rules/zoho-crm/zoho-crm-asyncapi-spectral-rules/)
- [Zoho CRM API Rules](https://apis.io/rules/zoho-crm/zoho-crm-rules/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Zoho Crm Authentication](https://apis.io/security/zoho-crm/zoho-crm-authentication/)
- [Zoho Crm Domain Security](https://apis.io/security/zoho-crm/zoho-crm-domain-security/)
- [Zoho Crm Trust Center](https://apis.io/security/zoho-crm/zoho-crm-trust-center/)
- [Zoho Crm Vulnerability Disclosure](https://apis.io/security/zoho-crm/zoho-crm-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Zoho Crm Scopes](https://apis.io/scopes/zoho-crm/zoho-crm-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Zoho Crm Plans Pricing](https://apis.io/plans/zoho-crm/zoho-crm-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Zoho Crm Rate Limits](https://apis.io/rate-limits/zoho-crm/zoho-crm-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.zoho.com/crm/)
- [Documentation](https://www.zoho.com/crm/developer/docs/api/v8/)
- [Getting started](https://www.zoho.com/crm/developer/docs/api/v8/oauth-overview.html)
- [API reference](https://www.zoho.com/crm/developer/docs/api/v8/list-available-rest-apis.html)
- [Pricing](https://www.zoho.com/crm/zohocrm-pricing.html)
- [Sign up](https://www.zoho.com/crm/signup.html)
- [Support](https://help.zoho.com/portal/en/community/zoho-crm)
- [Blog](https://www.zoho.com/crm/blog/feed/)
- [Security](https://bugbounty.zohocorp.com/bb/info)
- [Compliance](https://www.zoho.com/compliance.html)
- [Terms of service](https://www.zoho.com/terms.html)
- [Privacy policy](https://www.zoho.com/privacy.html)
- [GitHub](https://github.com/zoho)
- [Status](https://status.zoho.com/)

## API Evangelist rating

**Kin Score 84.4** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 76.7 |
| Contract quality | 73.8 |
| Contract governance | 35.6 |
| Operational transparency | 92.1 |
| Developer ergonomics | 82.7 |
| Access clarity | 92.1 |

**Agent readiness 44.2** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | documented (partial credit) |
| Auth Clarity | served (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | — |

**Regulatory alignment 45.1** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/zoho-crm/](https://apis.io/providers/zoho-crm/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Zoho CRM: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/zoho-crm/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
