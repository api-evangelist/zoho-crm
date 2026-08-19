---
name: Subscribe to Zoho CRM record change notifications
description: Register a notify_url channel so Zoho CRM POSTs callbacks on record create, edit and delete events, and keep the channel alive.
api: openapi/zoho-crm-notifications-openapi.json, asyncapi/zoho-crm-notifications-asyncapi.yml
operations: [createNotifications, getNotifications, updateNotificationDetails, updateNotificationInfo, disableNotifications]
---

# Subscribe to Zoho CRM record notifications

Zoho CRM's event surface is "Instant Notifications": you register a channel pointing at your
own HTTPS endpoint, and Zoho POSTs JSON callbacks when subscribed operations happen.

## Preconditions

- `Authorization: Zoho-oauthtoken {access_token}`.
- Scopes: `ZohoCRM.notifications.CREATE` / `.READ` / `.UPDATE` / `.DELETE`.
- A publicly reachable HTTPS `notify_url` that responds quickly.

## Steps

1. `createNotifications` — `POST /actions/watch` with `channel_id`, `notify_url`, and
   `events` naming module + operation pairs such as `Leads.create`, `Contacts.edit`,
   `Deals.delete`, `Accounts.all`.
2. `getNotifications` — `GET /actions/watch` to list active channels and their expiry.
3. `updateNotificationDetails` (`PUT`) or `updateNotificationInfo` (`PATCH`) —
   `/actions/watch` to extend or amend a channel before it expires.
4. `disableNotifications` — `DELETE /actions/watch` to tear a channel down.

## Rules

- Channels expire. Renew on a schedule; do not rely on a channel surviving indefinitely.
- Treat callbacks as **notifications, not payloads** — re-read the record with `getRecord`
  before acting on it, so a replayed or out-of-order callback cannot make you act on stale
  state.
- Callbacks are unauthenticated from your side of the wire: validate the channel id and the
  record before writing anything back.

The callback surface is modelled in `asyncapi/zoho-crm-notifications-asyncapi.yml`.
