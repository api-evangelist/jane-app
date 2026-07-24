---
name: Record a clinical observation and care plan
description: Create and update medical-record observations and care plans for a patient.
api: openapi/jane-app-jdp-openapi.yml
operations:
- createObservation
- getObservation
- updateObservation
- listObservations
- createCarePlan
- createCarePlanActivity
scopes:
- observations:create
- observations:read
- observations:update
- care_plans:create
generated: '2026-07-24'
method: generated
source: openapi/jane-app-jdp-openapi.yml
---

## Goal
Write clinical documentation — observations and care plans — into a patient's Jane medical record.

## Auth
OAuth 2.0 + PKCE bearer JWT, `Content-Type: application/json`. Requires the clinical write scopes below, consented by the practitioner. Data is limited to the practitioner's accessible patients in the clinic.

## Steps
1. **Create an observation.** POST `createObservation` with the observation body for the target patient (scope `observations:create`).
2. **Read it back.** `getObservation` by id (scope `observations:read`); or `listObservations` for the current user's accessible patients.
3. **Amend if needed.** PATCH `updateObservation` by id (scope `observations:update`).
4. **Add a care plan.** POST `createCarePlan`, then `createCarePlanActivity` to attach activities (scope `care_plans:create`).

## Conventions
- IDs are UUID `public_id` strings.
- Errors are custom JSON (not RFC 9457): `{ errors: [ { id, message, details } ] }` on validation/conflict, `{ error }` on auth failures. A `409` id `DUPLICATE_RECORD` signals an existing record.
- No request Idempotency-Key is supported — guard against duplicate POSTs client-side.
