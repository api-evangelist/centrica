# Centrica

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

**Areas:** Energy · United Kingdom · Utilities · Electricity · Gas · Smart Metering · Energy Retail · Energy Markets · Ireland · Field Service Management

## Centrica on APIs.io

Everything profiled for Centrica is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/centrica/](https://apis.io/providers/centrica/)** — or go straight to one of the APIs or properties below.

### APIs (1)

- [Centrica Oauth2 API](https://apis.io/apis/centrica/centrica-oauth2-api/) — The Oauth2 API from Centrica — 1 operation(s) for oauth2.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [centrica-fieldops](https://apis.io/servers/centrica/centrica-fieldops/)

#### Collections (1)

Postman and Open Collection request collections.

- [Identity API](https://apis.io/collections/centrica/open-centrica-fieldops-identity-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Centrica Fieldops Identity Api Overlay](https://apis.io/overlays/centrica/centrica-fieldops-identity-api-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Centrica Authentication](https://apis.io/security/centrica/centrica-authentication/)
- [Centrica Domain Security](https://apis.io/security/centrica/centrica-domain-security/)
- [Centrica Vulnerability Disclosure](https://apis.io/security/centrica/centrica-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Centrica Plans](https://apis.io/plans/centrica/centrica-plans/)

#### Rate limits (1)

Published request limits.

- [Centrica Rate Limits](https://apis.io/rate-limits/centrica/centrica-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.centrica.com/)
- [Documentation](https://api-developer.dev.fieldops.centrica.com/)
- [API reference](https://api-developer.dev.fieldops.centrica.com/apis)
- [Sign up](https://api-developer.dev.fieldops.centrica.com/signup)
- [Blog](https://www.britishgas.co.uk/business/blog)
- [Security](https://www.britishgas.co.uk/global-maintenance/responsible-disclosure.html)
- [Terms of service](https://www.britishgas.co.uk/terms-and-conditions.html)
- [Privacy policy](https://www.britishgas.co.uk/privacy-policy.html)
- [GitHub](https://github.com/ConnectedHomes)

## API Evangelist rating

**Kin Score 48.2** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 45.9 |
| Contract governance | 4.5 |
| Operational transparency | 44.7 |
| Developer ergonomics | 49.4 |
| Access clarity | 55.3 |

**Agent readiness 32.2** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 32.0** — Energy & Utilities

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/centrica/](https://apis.io/providers/centrica/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Centrica: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/centrica/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
