---
name: Read a patient and their appointments
description: List/find a patient, then read that patient's appointment history in a Jane clinic.
api: openapi/jane-app-jdp-openapi.yml
operations:
- searchPatients
- getPatients
- getPatient
- listAppointmentsVersioned
- getAnAppointment
scopes:
- patients:read
- appointments:read
generated: '2026-07-24'
method: generated
source: openapi/jane-app-jdp-openapi.yml
---

## Goal
Locate a patient in a Jane clinic and read their one-on-one appointment bookings.

## Auth
OAuth 2.0 Authorization Code + PKCE (S256) over OIDC. Send `Authorization: Bearer <RS256 JWT>` and `Content-Type: application/json`. The token is clinic- and practitioner-scoped; call the clinic host in the token `aud` claim. Access tokens live 5 minutes — refresh proactively.

## Steps
1. **Find the patient.** For a free-text lookup POST `searchPatients` with body `{ "search": { "co": "<name/email/phone>" }, "page": { "limit": 50 } }` (PII stays out of the URL). For structured filters use `getPatients` with `field[operator]=value` (e.g. `updated_at[gte]=2025-01-01T00:00:00Z`). Read the returned `public_id`.
2. **Read the patient.** Call `getPatient` with the `public_id`.
3. **List appointments.** Call `listAppointmentsVersioned` filtered by `patient_id[eq]=<uuid>` (also supports staff_member_id, location_id, treatment_id, start_at, end_at). This returns one-on-one bookings only.
4. **Read one appointment.** Call `getAnAppointment` with its id for full detail.

## Conventions
- Cursor pagination: re-request with `page.cursor` = previous `cursor` while `hasNextPage` is true.
- Rate limit 100/min/endpoint/clinic; on `429` honor `Retry-After`.
- Requires scopes `patients:read` and `appointments:read`, granted at authorization.
