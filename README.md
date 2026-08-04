# Jane (jane-app)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Jane is a cloud-based practice management platform for health and wellness clinics, headquartered in North Vancouver, Canada, with regional data residency across Canada, the USA, the United Kingdom, and Australia. It combines online booking, scheduling, charting and clinical documentation (with AI-assisted notes), insurance billing, payments, patient intake, a patient mobile app, and telehealth in one system for interdisciplinary clinics — physiotherapy, massage therapy, chiropractic, counselling, midwifery, and more.

The **Jane Developer Platform** (developers.jane.app) exposes a documented, proprietary **REST API** that lets approved Technology Partners build **"Jane Extensions"** — practitioner-authorized integrations that read and write clinic data. It is **not** an HL7 FHIR / SMART-on-FHIR surface: authentication is OAuth 2.0 with PKCE over OpenID Connect (Keycloak), using RS256 JWT bearer tokens and granular scopes (e.g. `observations:read`). The API is per-clinic and date-versioned in the URL path (`https://<clinic>/api/YYYY-MM-DD/`).

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/jane-app/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/jane-app/refs/heads/main/apis.yml)

## Tags

- Healthcare
- Canada
- Practice Management
- EHR
- EMR
- Scheduling
- Clinical Documentation
- Telehealth
- Health and Wellness
- REST API
- OAuth2
- Webhooks

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

### Jane Patients API

Retrieve, list, and free-text search patient records for the practitioner's accessible patients within a clinic.

- **Human URL:** [https://developers.jane.app/reference](https://developers.jane.app/reference)

### Jane Appointments API

Retrieve and list one-on-one appointment bookings, filtered by patient, staff member, location, treatment, and time window.

- **Human URL:** [https://developers.jane.app/reference](https://developers.jane.app/reference)

### Jane Practice and Scheduling API

Read clinic reference and scheduling data — locations, staff members, disciplines, treatments, and company details.

- **Human URL:** [https://developers.jane.app/reference](https://developers.jane.app/reference)

### Jane Medical Records API

Create, read, update, and list clinical medical-record data — observations, care plans and activities, and medications (with change history).

- **Human URL:** [https://developers.jane.app/reference](https://developers.jane.app/reference)

### Jane Documents API

Upload documents (PDF, JPEG, PNG up to 50 MB) to receive a referenceable document ID, and retrieve previously uploaded documents.

- **Human URL:** [https://developers.jane.app/reference](https://developers.jane.app/reference)

### Jane Webhooks API

Register, list, retrieve, and deregister signed webhook subscriptions for clinic event notifications.

- **Human URL:** [https://developers.jane.app/reference](https://developers.jane.app/reference)

### Jane Extensions API

Create, read, update, delete, and list Jane Extensions, and browse the catalog of approved extensions.

- **Human URL:** [https://developers.jane.app/reference](https://developers.jane.app/reference)

## Authentication

- **Scheme:** OAuth 2.0 Authorization Code with PKCE, over OpenID Connect
- **Identity Provider:** Keycloak (`realms/<realm>/protocol/openid-connect/{auth,token}`)
- **Tokens:** RS256-signed JWT bearer (access token 5 min, refresh token 30 min)
- **Scopes:** resource-scoped, e.g. `observations:read`, `observations:create`
- **Not FHIR:** no SMART-on-FHIR scope grammar, no FHIR CapabilityStatement

## Common Properties

- [Website](https://jane.app/)
- [Developer Portal](https://developers.jane.app/)
- [Documentation](https://developers.jane.app/docs/getting-started)
- [API Reference](https://developers.jane.app/reference)
- [GitHub Organization](https://github.com/janeapp)
- [Pricing](https://jane.app/pricing)
- [Blog](https://jane.app/blog)
- [Security](https://jane.app/security)
- [Integrations](https://jane.app/integrations)
- [llms.txt endpoint index](llms/jane-app-llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
