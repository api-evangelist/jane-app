---
name: Subscribe to appointment webhooks
description: Register, verify, and manage signed appointment-event webhook subscriptions.
api: openapi/jane-app-jdp-openapi.yml
operations:
- postWebhooks
- getWebhooks
- getWebhook
- deleteWebhook
scopes:
- webhooks:create
- webhooks:read
- webhooks:delete
generated: '2026-07-24'
method: generated
source: openapi/jane-app-jdp-openapi.yml
---

## Goal
Receive real-time appointment events from a Jane clinic instead of polling.

## Auth
OAuth 2.0 + PKCE bearer JWT. Only owner / full-permission staff may register webhooks. Requires `webhooks:create`, `webhooks:read`, `webhooks:delete`.

## Steps
1. **Register.** POST `postWebhooks` with `{ "event_topic": "APPOINTMENT_BOOKED", "target_url": "https://<you>/hook" }`. The response returns a signing secret **once** — store it securely; it cannot be retrieved again. Topics: `APPOINTMENT_BOOKED`, `APPOINTMENT_CANCELLED`, `APPOINTMENT_RESCHEDULED`, `APPOINTMENT_UNCANCELLED`.
2. **Verify deliveries.** Each POST to your `target_url` carries `X-Jane-Signature: sha256=<hmac>` and `X-Jane-Timestamp`. Recompute the HMAC-SHA256 over the body with your secret and constant-time compare. Payloads are notification-only (no PII) — carry `event_id`, `event_topic`, `event_timestamp`, `appointment_id`, `clinic_guid`, `version`.
3. **Fetch detail.** Use `event_id` for idempotent dedup, then call `getAnAppointment`/`listAppointmentsVersioned` for the changed data.
4. **List / inspect / remove.** `getWebhooks`, `getWebhook` by id, `deleteWebhook` to deregister.

## Conventions
- `target_url` must be HTTPS.
- Rate limit and cursor-pagination conventions apply as elsewhere.
