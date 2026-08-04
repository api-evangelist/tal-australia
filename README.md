# TAL (tal-australia)

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

TAL is Australia's largest life insurer by inforce risk-only premium (NMG Consulting, 2023), owned by Japan's Dai-ichi Life Group and underwriting through TAL Life Limited (ABN 70 050 109 450, AFSL 237848). Operating in the Australian market for roughly 150 years, TAL writes life cover, income protection, total and permanent disability and critical illness, and reports paying $4.7 billion in benefits to 57,000 customers and their families in its most recent year. It distributes through three channels — financial advisers via the login-gated TAL Adviser Centre, group insurance inside superannuation funds, and direct/embedded offers including backd by TAL, a payroll-embedded product built with Sydney insurtech Cover Genius. TAL's API posture is partner-gated and closed: no developer portal, no public API reference, no downloadable OpenAPI, and no published ACORD or AL3 position. The only integration surfaces are the adviser extranet behind a login and bilateral partner arrangements with super funds, payroll platforms and distributors. Australia's Consumer Data Right was designated to extend to insurance but was deferred, so no open-insurance mandate forces a public surface here.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/tal-australia/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/tal-australia/refs/heads/main/apis.yml)

## Tags

- Insurance
- Australia
- Life Insurance
- Income Protection
- Group Insurance
- Superannuation
- Underwriting
- Claims
- Carrier
- Embedded Insurance
- Partner Gated
- No Public API
- OpenID Connect
- GraphQL
- Identity

## Timestamps

- **Created:** 2026-07-25
- **Modified:** 2026-07-25

## APIs

TAL publishes no public, self-serve API — but it is **not API-less, it is
API-private**. Enumerating certificate transparency for `*.tal.com.au` (832
distinct names) and probing what actually resolves turned up a real partner API
estate on 2026-07-25:

| Surface | Host | Anonymous result |
|---|---|---|
| Partner identity (OpenID Connect) | `login.talpartner.tal.com.au` | **200** — full OIDC + RFC 8414 discovery |
| ACP identity | `auth.acp.tal.com.au` | **200** — OIDC discovery |
| Claims Assist identity | `auth.claimsassist.tal.com.au` | **200** — OIDC discovery |
| Underwriting Rules Engine GraphQL | `ure-prod-graphql-app.tal.com.au/graphql` | **200 on POST** — root type `CaseQuery`, introspection filtered |
| Group Life B2B common service | `common.glsb2b.tal.com.au` | **401** — `WWW-Authenticate: Bearer` |
| Group Life B2B (uwin/uwout/claimsin/claimsout/clpapi/delivery) | `*.glsb2b.tal.com.au` | 403 / 502 / 200 (Azure Function shell) |
| Per-distributor API hosts | `iress.api`, `liferisk.api`, `omnium.api`, `partner.api` | 403 or connection-refused — edge-restricted to partners |
| Group HQ partner portal | `www.grouphq.tal.com.au` | **200** — login-gated super-fund partner portal |

The hostnames a reviewer would guess — `developer.tal.com.au`,
`api.developer.tal.com.au`, `apicatalog.tal.com.au`, `apiportal.tal.com.au`,
`gateway.tal.com.au` — all hold TLS certificates (with full dev/qa/preprod/green
ladders behind them) but **do not resolve in public DNS**. TAL built a developer
portal and an API catalogue and kept them inside.

The `iress.api.tal.com.au` hostname is the first hard evidence of TAL's adviser
software integration seam: TAL names no third-party planning software anywhere
on its public pages.

No OpenAPI, Swagger, AsyncAPI, `.proto` or Postman collection is published on any
TAL-controlled host, so this repo has no `openapi/` directory. The URE GraphQL
endpoint answers, but field-level introspection is filtered, so no SDL exists to
capture and none is fabricated. No webhook or event catalog is documented.

The closest human integration surfaces remain
[adviser.tal.com.au](https://adviser.tal.com.au/) — the **TAL Adviser Centre**,
a Sitecore extranet for licensed financial advisers — and
[Group HQ](https://www.grouphq.tal.com.au/) for superannuation partners. Both are
**login walls, not developer portals**.

## Harvested artifacts

- `llms/tal-australia-llms.txt` — TAL's own published `llms.txt` (71 KB, last
  modified 2026-06-29), harvested verbatim. The only machine-consumable document
  TAL publishes to the open web.
- `well-known/` — index plus four harvested discovery documents (three OIDC
  configurations and one RFC 8414 authorization-server metadata document).
- `authentication/`, `scopes/` — the partner auth model and the published scope
  set (standard OIDC scopes only; no business-domain scopes exist publicly).
- `graphql/` — the URE endpoint, its observed responses, and an explicit record
  that the schema is gated.
- `conformance/` — 25 standards checked, each with evidence: OAuth 2.0, OIDC,
  PKCE, PAR, DPoP, CIBA and device code conform; OpenAPI, AsyncAPI, RFC 9457,
  RFC 9116, RFC 8594, ACORD, CDR, FHIR and FAPI do not.
- `errors/`, `conventions/`, `lifecycle/`, `packages/`, `security/` — derived
  and probed profiles, including the measured absences (no idempotency contract,
  no pagination, no rate-limit signalling, no status page, no changelog, no
  security.txt, no SDKs).

**ACORD posture: no ACORD reference found.** Searching tal.com.au,
adviser.tal.com.au and backd.com.au for ACORD, AL3, ACORD XML and NGDS returned
zero occurrences — consistent with the market, since ACORD AL3 / IVANS agency
download is a US property-and-casualty artifact while Australian life insurance
moves adviser data through commercial planning and quoting software under
bilateral arrangements. TAL names no such integration publicly either.

Of the four insurance verbs, **none of quote, bind, issue or FNOL is exposed
programmatically**. Quoting and application live inside the gated Adviser
Centre; claims are lodged through web forms at
`www.tal.com.au/claims/make-a-claim`.

## Why this record matters

Australia has the legal machinery for open insurance and no live obligation.
APRA supervises prudentially, and the Consumer Data Right that already opened
banking and energy was designated to extend to general insurance and then
deferred and de-prioritised — so the CDR seam that made Australian banking
legible stops before insurance. TAL sits squarely in that gap: a dominant
carrier with no regulatory forcing function to publish anything and no
commercial reason to self-serve when its distribution runs through advisers,
super funds and named partners. Its most API-shaped asset is not even its own —
*backd by TAL* is built on Cover Genius, the Sydney embedded-insurance company
that does publish a real API, and that consumer brand currently serves a
"Coming Soon" placeholder at [backd.com.au](https://backd.com.au/).

Recording that shape accurately is the point — and the second pass sharpened it.
The absence is not of APIs; TAL has an identity tenant, a GraphQL underwriting
engine and a bearer-protected B2B estate. The absence is of *documentation,
registration and self-service*. A carrier can run a full API programme and still
be invisible to everyone it did not sign a contract with.

## Links

- [TAL](https://www.tal.com.au/)
- [About TAL](https://www.tal.com.au/about-us)
- [TAL Adviser Centre (login-gated)](https://adviser.tal.com.au/)
- [TAL Group HQ (login-gated superannuation partner portal)](https://www.grouphq.tal.com.au/)
- [Adviser Partners](https://www.tal.com.au/adviser-partners)
- [Superannuation Partners](https://www.tal.com.au/superannuation-partners)
- [Contact / Support](https://www.tal.com.au/contact-us)
- [Insurance FAQs](https://www.tal.com.au/tools-and-faqs/insurance-faqs)
- [Media Centre](https://www.tal.com.au/about-us/media-centre)
- [Slice of Life Blog](https://www.tal.com.au/slice-of-life-blog)
- [Security](https://www.tal.com.au/security)
- [Privacy Policy](https://www.tal.com.au/privacy-policy)

## Review

See [review.yml](review.yml) for the full probe log, HTTP statuses, ACORD
posture and auth-model findings.
