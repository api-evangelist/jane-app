# Jane

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

Jane is a cloud-based practice management platform for health and wellness clinics, headquartered in North Vancouver, Canada, with regional data residency across Canada, the USA, the United Kingdom, and Australia. Jane combines online booking, scheduling, charting and clinical documentation (including AI-assisted notes), insurance billing, payments, patient intake, a patient mobile app, and telehealth in a single system used by interdisciplinary clinics — physiotherapy, massage therapy, chiropractic, counselling, midwifery, and more. The Jane Developer Platform (developers.jane.app) exposes a documented REST API that lets approved Technology Partners build "Jane Extensions" — practitioner-authorized integrations that read and write clinic data. Authentication is OAuth 2.0 with PKCE over OpenID Connect (Keycloak realms), using RS256 JWT bearer access tokens and granular scopes (e.g. observations:read). The API is date-versioned in the URL path and is per-clinic (https://<clinic>/api/YYYY-MM-DD/), covering patients, appointments, locations, staff, disciplines, treatments, medical records (observations, care plans, medications), document uploads, webhooks, and extension management. Jane is not FHIR/HL7-based: it is a proprietary REST practice-management API rather than a SMART-on-FHIR EHR interoperability surface.

**Areas:** Healthcare · Canada · Practice Management · Electronic Health Records · Scheduling · Clinical Documentation · Telehealth · Health and Wellness · REST API · Authentication · Webhook

## Jane on APIs.io

Everything profiled for Jane is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/jane-app/](https://apis.io/providers/jane-app/)** — or go straight to one of the APIs or properties below.

### APIs (21)

- [Jane Patients API](https://apis.io/apis/jane-app/jane-patients-api/) — Retrieve, list, and free-text search patient records for the practitioner's accessible patients within a clinic. Free-text search is a POST-body endpoint so…
- [Jane Appointments API](https://apis.io/apis/jane-app/jane-appointments-api/) — Retrieve and list one-on-one appointment bookings for a clinic, with filtering by patient, staff member, location, treatment, and time window. Part of the…
- [Jane Practice and Scheduling API](https://apis.io/apis/jane-app/jane-scheduling-api/) — Read clinic reference and scheduling data — locations, staff members, disciplines, treatments, and company details — that underpin booking and practice…
- [Jane Medical Records API](https://apis.io/apis/jane-app/jane-medical-records-api/) — Create, read, update, and list clinical medical-record data for a patient — observations, care plans and care plan activities, and medications (including…
- [Jane Documents API](https://apis.io/apis/jane-app/jane-documents-api/) — Upload document files (PDF, JPEG, PNG up to 50 MB) to receive a document ID that can be referenced in other API calls, and retrieve a previously uploaded…
- [Jane Webhooks API](https://apis.io/apis/jane-app/jane-webhooks-api/) — Register, list, retrieve, and deregister webhook subscriptions so partners receive signed event notifications for a clinic. The signing secret is returned…
- [Jane Extensions API](https://apis.io/apis/jane-app/jane-extensions-api/) — Create, read, update, delete, and list Jane Extensions, and browse the catalog of approved extensions available to clinics. This is the management surface…
- [Jane Appointments API](https://apis.io/apis/jane-app/jane-app-appointments-api/) — The Appointments API from Jane — 2 operation(s) for appointments.
- [Jane Catalog API](https://apis.io/apis/jane-app/jane-app-catalog-api/) — The Catalog API from Jane — 2 operation(s) for catalog.
- [Jane Company API](https://apis.io/apis/jane-app/jane-app-company-api/) — The Company API from Jane — 1 operation(s) for company.
- [Jane Disciplines API](https://apis.io/apis/jane-app/jane-app-disciplines-api/) — The Disciplines API from Jane — 2 operation(s) for disciplines.
- [Jane Document Uploads API](https://apis.io/apis/jane-app/jane-app-documentuploads-api/) — The DocumentUploads API from Jane — 2 operation(s) for documentuploads.
- [Jane Extensions API](https://apis.io/apis/jane-app/jane-app-extensions-api/) — The Extensions API from Jane — 2 operation(s) for extensions.
- [Jane Locations API](https://apis.io/apis/jane-app/jane-app-locations-api/) — The Locations API from Jane — 2 operation(s) for locations.
- [Jane Medications API](https://apis.io/apis/jane-app/jane-app-medications-api/) — The Medications API from Jane — 3 operation(s) for medications.
- [Jane Observations API](https://apis.io/apis/jane-app/jane-app-observations-api/) — The Observations API from Jane — 2 operation(s) for observations.
- [Jane Patients API](https://apis.io/apis/jane-app/jane-app-patients-api/) — The Patients API from Jane — 3 operation(s) for patients.
- [Jane Treatments API](https://apis.io/apis/jane-app/jane-app-treatments-api/) — The Treatments API from Jane — 2 operation(s) for treatments.
- [Jane Webhooks API](https://apis.io/apis/jane-app/jane-app-webhooks-api/) — The Webhooks API from Jane — 2 operation(s) for webhooks.
- [Jane Care Plans API](https://apis.io/apis/jane-app/jane-app-care-plans-api/) — The Care Plans API from Jane — 4 operation(s) for care plans.
- [Jane Staff Members API](https://apis.io/apis/jane-app/jane-app-staff-members-api/) — The Staff Members API from Jane — 2 operation(s) for staff members.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Jane App Webhooks](https://apis.io/asyncapis/jane-app/jane-app-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [jane-jdp](https://apis.io/servers/jane-app/jane-jdp/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Jane App Agentic Access](https://apis.io/agentic-access/jane-app/jane-app-agentic-access/)

#### Collections (1)

Postman and Open Collection request collections.

- [JDP API](https://apis.io/collections/jane-app/open-jane-app-jdp/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Jane App Jdp Overlay](https://apis.io/overlays/jane-app/jane-app-jdp-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Jane App Authentication](https://apis.io/security/jane-app/jane-app-authentication/)
- [Jane App Domain Security](https://apis.io/security/jane-app/jane-app-domain-security/)
- [Jane App Trust Center](https://apis.io/security/jane-app/jane-app-trust-center/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Jane App Scopes](https://apis.io/scopes/jane-app/jane-app-scopes/)

#### Plans and pricing (2)

Published plans, tiers and prices.

- [Jane App Plans Pricing](https://apis.io/plans/jane-app/jane-app-plans-pricing/)
- [Jane App Price Estimates](https://apis.io/plans/jane-app/jane-app-price-estimates/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://jane.app/)
- [Documentation](https://developers.jane.app/docs/getting-started)
- [Getting started](https://developers.jane.app/docs/getting-started)
- [API reference](https://developers.jane.app/reference)
- [Pricing](https://jane.app/pricing)
- [Support](https://jane.app/contact)
- [Blog](https://jane.app/blog)
- [Security](https://jane.app/security)
- [Compliance](https://jane.app/security-and-trust)
- [Terms of service](https://jane.app/terms)
- [Privacy policy](https://jane.app/privacy)
- [GitHub](https://github.com/janeapp)
- [Status](https://jane.statuspage.io/)

## API Evangelist rating

**Kin Score 58.2** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 64.3 |
| Contract quality | 60.1 |
| Contract governance | 18.2 |
| Operational transparency | 36.8 |
| Developer ergonomics | 47.0 |
| Access clarity | 78.9 |

**Agent readiness 51.9** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | verified |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | distinct |

**Regulatory alignment 47.7** — Health

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/jane-app/](https://apis.io/providers/jane-app/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Jane: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/jane-app/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
