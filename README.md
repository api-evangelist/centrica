# Centrica (centrica)

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

## Maintainers

- Kin Lane — kin@apievangelist.com
