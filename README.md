# Centrica (centrica)

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

Centrica plc is the FTSE-listed British energy and services group behind British Gas, the United Kingdom's largest household energy supplier, along with Bord Gais Energy in Ireland, Centrica Business Solutions, Centrica Energy (its wholesale power, gas and LNG trading arm) and the Hive connected-home brand. It sits across the whole value chain — upstream gas and storage at Rough, generation and battery flexibility, wholesale trading and route-to-market, retail supply to roughly ten million UK homes, and a field-service engineering business — after exiting North America with the sale of Direct Energy to NRG in January 2021 to refocus on the UK and Ireland. Its API posture is honestly closed: Britain mandated the smart-metering INFRASTRUCTURE (the licensed Smart DCC monopoly and the SMETS2 rollout) rather than a consumer data right, so Centrica has no Consumer Data Right, no Green Button and no standards-conformant consumer usage endpoint. The DESNZ non-domestic smart meter data access requirement that does bind it is discharged by a written request answered within ten working days, not by an API. Household consumers reach their own data only through the British Gas app and account login; business customers through the Energy360 DataView portal. The single publicly reachable developer surface found is the Centrica FieldOps Azure API Management developer portal — a partner field-operations platform in its development environment — and Centrica publishes no open grid or market data of its own, leaving that to NESO, Elexon and the DNOs.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/centrica/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/centrica/refs/heads/main/apis.yml)

## Tags

- Energy
- United Kingdom
- Utilities
- Electricity
- Gas
- Smart Metering
- Energy Retail
- Energy Markets
- Ireland
- Field Service

## Timestamps

- **Created:** 2026-07-27
- **Modified:** 2026-07-27

## APIs

### Centrica FieldOps Identity API

Token-issuing API on the Centrica FieldOps API Management platform, published on Centrica's Azure API Management developer portal. A single POST /oauth2/token operation exchanges an OAuth2 client_credentials grant (client_id + client_secret, form-encoded) for a bearer access token used against the FieldOps WorkOrder, Opportunity and Appointment Slots APIs. Harvested verbatim from the portal's development environment on 2026-07-27; the production hosts api.fieldops.centrica.com and api-developer.fieldops.centrica.com both answer 403 anonymously. Calls also carry an Azure APIM subscription key (Ocp-Apim-Subscription-Key header or subscription-key query parameter).

- **Human URL:** [https://api-developer.dev.fieldops.centrica.com/api-details#api=identity-api](https://api-developer.dev.fieldops.centrica.com/api-details#api=identity-api)
- **Base URL:** `https://api.dev.fieldops.centrica.com/api/v1/identity`

#### Tags

- Identity
- OAuth2
- Field Service
- Partner

#### Properties

- [OpenAPI](openapi/centrica-fieldops-identity-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://api-developer.dev.fieldops.centrica.com/apis)
- [Developer Portal](https://api-developer.dev.fieldops.centrica.com/)

## Common Properties

- [Website](https://www.centrica.com/)
- [Documentation](https://api-developer.dev.fieldops.centrica.com/)
- [Developer Portal](https://api-developer.dev.fieldops.centrica.com/)
- [Sign Up](https://api-developer.dev.fieldops.centrica.com/signup)
- [Plans](https://api-developer.dev.fieldops.centrica.com/products)
- [Blog](https://www.britishgas.co.uk/business/blog)
- [LinkedIn](https://www.linkedin.com/company/centrica)
- [GitHub Organization](https://github.com/ConnectedHomes)

## Mandate Posture

| Dimension | Finding |
| --- | --- |
| Home market | United Kingdom (plus Republic of Ireland via Bord Gais Energy) |
| Mandate regime | `smart-meter-infrastructure` — Smart DCC / SMETS2, a licensed infrastructure monopoly, **not** a consumer data right |
| Mandate status | `designated-not-live` — the DESNZ non-domestic data-access obligation is in force (1 Dec 2022 on request, 1 Oct 2024 default offer) but is discharged by a written request answered within ten working days, with no API |
| Data standard | No standard reference found — no Green Button/ESPI, no CDR Consumer Data Standards, no IEEE 2030.5, no OpenADR, no OCPP/OCPI, no IEC CIM |
| Consumer data API | No — British Gas app / account login for households, Energy360 DataView login for business |
| Open market data | No — Centrica publishes none; NESO, Elexon and the DNOs publish the open UK energy data |
| Access gate | `partner-only` — the FieldOps portal offers self-serve sign-up in its development environment, but production hosts answer 403 and the WorkOrder / Opportunity / Appointment Slots APIs are invisible anonymously |
| Auth model | OAuth2 client_credentials bearer tokens layered under Azure APIM subscription keys |

See [review.yml](review.yml) for every URL probed, its HTTP status, and the full mandate-versus-implementation record.

## Artifacts

Produced by the API Evangelist enrichment pipeline on 2026-07-27. Where a thing genuinely does
not exist, the artifact records the absence with the probes that established it — that negative
evidence is the point for a provider this closed.

| Artifact | File | Method | Finding |
| --- | --- | --- | --- |
| OpenAPI | [openapi/](openapi/centrica-fieldops-identity-api-openapi.yml) | searched | One operation, exported verbatim from Centrica's own Azure APIM instance |
| Overlay | [overlays/](overlays/centrica-fieldops-identity-api-overlay.yaml) | generated | Our enhancements and the spec's gaps; the harvest is never mutated |
| Well-known | [well-known/](well-known/centrica-well-known.yml) | searched | 5 hosts probed, 3 documents found |
| security.txt | [well-known/](well-known/centrica-security.txt) | searched | On britishgas.co.uk; no Contact or Expires field, so RFC 9116 partial |
| OIDC discovery | [well-known/](well-known/centrica-openid-configuration.json) | searched | Real discovery doc on centrica.com — Umbraco CMS member auth, not a developer API |
| Authentication | [authentication/](authentication/centrica-authentication.yml) | derived | APIM subscription key in header and query |
| Conventions | [conventions/](conventions/centrica-conventions.yml) | derived | No idempotency, no pagination, no request-id, no error envelope |
| Conformance | [conformance/](conformance/centrica-conformance.yml) | derived | OpenAPI/OAuth2/OIDC/JWKS/PKCE yes; every energy data standard no |
| Lifecycle | [lifecycle/](lifecycle/centrica-lifecycle.yml) | searched | URI-path v1; no deprecation policy, no changelog, no status page |
| Plans | [plans/](plans/centrica-plans.yml) | searched | The two stock APIM products, unpriced |
| Rate limits | [rate-limits/](rate-limits/centrica-rate-limits.yml) | searched | 5 calls/min, 100 calls/week on Starter; unlimited on approval |
| Sandbox | [sandbox/](sandbox/centrica-sandbox.yml) | searched | No curated sandbox — an internal DEV environment left publicly reachable |
| Packages | [packages/](packages/centrica-packages.yml) | searched | Zero first-party SDKs across eight registries and both GitHub orgs |
| Data model | [data-model/](data-model/centrica-data-model.yml) | derived | One entity; WorkOrder, Opportunity and AppointmentSlot named but unpublished |
| MCP | [mcp/](mcp/centrica-mcp.yml) | derived | No server. Centrica's own APIM record reports `isAgent: false`, `mcpProperties: null` |
| Agent skill | [skills/](skills/_index.yml) | generated | One skill on the one real operationId |
| llms.txt | [llms/](llms/centrica-llms.txt) | generated | Centrica publishes none; /llms.txt is 404 on every host |
| Domain security | [security/](security/centrica-domain-security.yml) | probed | TLS 1.3 + HSTS; DMARC p=reject on all four brand domains; no CAA, no DNSSEC |
| Vulnerability disclosure | [security/](security/centrica-vulnerability-disclosure.yml) | searched | British Gas responsible-disclosure policy; no bug bounty |

Not emitted, because the underlying thing does not exist: AsyncAPI/Webhooks, ChangeLog, CLI,
Components, ErrorCatalog, DeclineCodes, OAuthScopes, GraphQL, Protobuf, ToolCrosswalk,
StatusPage, Deprecation, Compliance, TrustCenter, Postman.

## Maintainers

- Kin Lane — kin@apievangelist.com
