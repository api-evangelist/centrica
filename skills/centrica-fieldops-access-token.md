---
name: centrica-fieldops-access-token
description: >-
  Obtain an OAuth 2.0 bearer access token from the Centrica FieldOps Identity API using
  partner client credentials, so that subsequent calls to the FieldOps WorkOrder, Opportunity
  and Appointment Slots APIs can be authorised. Covers both required credential layers, the
  exact request encoding, the string-typed token response fields, and the undocumented-error
  hazard.
api: openapi/centrica-fieldops-identity-api-openapi.yml
operations:
  - oauth-access-token
generated: '2026-07-27'
method: generated
source: openapi/centrica-fieldops-identity-api-openapi.yml
---

# Get a Centrica FieldOps access token

The Centrica FieldOps platform requires **two independent credentials on the same call**. Getting
either wrong produces a failure the API does not document, so check both before debugging
anything else.

## Before you start

You need, from Centrica's field-service business:

1. An **Azure API Management subscription key**, obtained by registering on the FieldOps developer
   portal (<https://api-developer.dev.fieldops.centrica.com/signup>) and subscribing to a product.
   The **Starter** product needs a subscription but no administrator approval; the **Unlimited**
   product needs administrator approval.
2. A **FieldOps `client_id` and `client_secret`** for the OAuth 2.0 client-credentials grant.
   These are issued under a commercial partner arrangement. There is no self-serve route to them
   and no published test credential — do not attempt to guess or reuse one.

Only the **development** environment is reachable without a partner arrangement. The production
gateway `api.fieldops.centrica.com` and production portal `api-developer.fieldops.centrica.com`
both return `403` to anonymous requests.

## Step 1 — call the token operation

Operation: `oauth-access-token` — `POST /oauth2/token`

Base URL: `https://api.dev.fieldops.centrica.com/api/v1/identity`

Send the subscription key **in the header** (`Ocp-Apim-Subscription-Key`). The spec also permits
it as a `subscription-key` query parameter; do not use that form — query strings are logged by
proxies and CDNs, which leaks the key.

The body is `application/x-www-form-urlencoded`, not JSON. The spec's own example is:

```
grant_type=client_credentials&client_id=<<clientid>>&client_secret=<<clientsecret>>
```

```
POST /api/v1/identity/oauth2/token HTTP/1.1
Host: api.dev.fieldops.centrica.com
Ocp-Apim-Subscription-Key: <your-apim-subscription-key>
Content-Type: application/x-www-form-urlencoded

grant_type=client_credentials&client_id=<client-id>&client_secret=<client-secret>
```

## Step 2 — read the response carefully

A `200` returns the schema `Oauth2TokenPost200ApplicationJsonResponse`. Only `token_type` and
`access_token` are required. **Every time field is a JSON string, not a number** — parse before
arithmetic:

| Field | Meaning |
|---|---|
| `token_type` | `Bearer` in the published example |
| `access_token` | the credential — treat as a secret |
| `expires_in` | lifetime in seconds, as a string (`"3599"` in the example) |
| `ext_expires_in` | extended lifetime in seconds, as a string |
| `expires_on` | Unix epoch seconds at which the token expires |
| `not_before` | Unix epoch seconds before which the token is invalid |
| `resource` | target resource identifier |

Refresh on `expires_on`, not on a hard-coded hour. Honour `not_before`: a token used too early is
rejected.

## Step 3 — use the token downstream

Present it as `Authorization: Bearer <access_token>` to the FieldOps business APIs the portal
advertises — **WorkOrder** (annual service visits, intermediate breakdowns), **Opportunity**
(electric-vehicle sales opportunities) and **Appointment Slots** (get and reserve appointments for
work orders). Keep sending the `Ocp-Apim-Subscription-Key` header alongside the bearer token; the
subscription key is enforced by the gateway independently of the token.

None of those three APIs is visible anonymously — the portal's anonymous API list returns exactly
one API. Their contracts come with your partner onboarding, not from this repository.

## Rules an agent must follow

- **Never log the request body or the `access_token`.** Both contain live secrets.
- **Cache the token; do not mint one per request.** The Starter product allows 5 calls/minute up to
  100 calls/week across *all* operations, so a token-per-request pattern exhausts the weekly quota
  in twenty requests.
- **There is no idempotency contract.** Do not blind-retry the token call. Back off and retry once
  with jitter at most.
- **Errors are undocumented.** The spec declares a `200` response and nothing else — no `4xx`, no
  `5xx`, no error schema and no `application/problem+json`. Do not assume a specific status code
  or body shape for a bad key, a bad secret or a quota breach; branch on `response.ok` and surface
  the raw status and body to a human.
- **No rate-limit headers are documented.** Track your own call budget against the product quota
  rather than expecting `RateLimit-*` or `Retry-After` to be present.
- This operation mints a credential. Do not expose it as an unattended agent tool without an
  authorised credential store and a human-approved policy.

## What this skill cannot do

There is no Centrica API for consumer or business energy usage, billing or account data. If the
task is "get a customer's smart meter readings", the answer is that no API exists: household data
lives behind the British Gas app login, business data behind the Energy360 DataView portal, and
the DESNZ non-domestic entitlement is fulfilled by a written request answered within ten working
days. See `review.yml`.
