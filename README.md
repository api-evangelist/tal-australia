# TAL (tal-australia)

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

## Timestamps

- **Created:** 2026-07-25
- **Modified:** 2026-07-25

## APIs

None. TAL publishes no public, self-serve API.

Every candidate developer hostname was probed on 2026-07-25:
`developer.tal.com.au`, `developers.tal.com.au` and `docs.tal.com.au` do not
resolve; `www.tal.com.au/developers`, `/api`, `/developer`, `/partners` and
`/integrations` all return 404; and `api.tal.com.au` resolves behind Azure Front
Door but returns an empty `application/json` 404 at root and at every probed
spec path — it is an internal backend for TAL's own web and mobile properties,
not a documented public API.

The closest thing to an integration surface is
[adviser.tal.com.au](https://adviser.tal.com.au/) — the **TAL Adviser Centre**,
a Sitecore extranet for licensed financial advisers. It returns HTTP 200, but
unknown paths redirect to `/404?item=…&user=extranet\Anonymous&site=TAC`, and its
navigation is products, Risk Academy training, claims, forms and documents. It is
a **partner/agent login wall, not a developer portal**.

No OpenAPI, Swagger, AsyncAPI, GraphQL SDL, `.proto` or Postman collection is
published on any TAL-controlled host, so this repo has no `openapi/` directory.
No webhook or event catalog is documented.

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

Recording the absence accurately is the point.

## Links

- [TAL](https://www.tal.com.au/)
- [About TAL](https://www.tal.com.au/about-us)
- [TAL Adviser Centre (login-gated)](https://adviser.tal.com.au/)
- [Adviser Partners](https://www.tal.com.au/adviser-partners)
- [Media Centre](https://www.tal.com.au/about-us/media-centre)
- [Slice of Life Blog](https://www.tal.com.au/slice-of-life-blog)
- [Security](https://www.tal.com.au/security)
- [Privacy Policy](https://www.tal.com.au/privacy-policy)

## Review

See [review.yml](review.yml) for the full probe log, HTTP statuses, ACORD
posture and auth-model findings.
