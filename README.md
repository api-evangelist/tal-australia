# TAL

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

TAL is Australia's largest life insurer by inforce risk-only premium (NMG Consulting, 2023), owned by Japan's Dai-ichi Life Group and underwriting through TAL Life Limited (ABN 70 050 109 450, AFSL 237848). Operating in the Australian market for roughly 150 years, TAL writes life cover, income protection, total and permanent disability and critical illness, and reports paying $4.7 billion in benefits to 57,000 customers and their families in its most recent year. It distributes through three channels — financial advisers via the login-gated TAL Adviser Centre, group insurance inside superannuation funds, and direct/embedded offers including backd by TAL, a payroll-embedded product built with Sydney insurtech Cover Genius. TAL is not API-less, it is API-private: certificate transparency and live probing surface a real partner API estate — an OpenID Connect partner identity tenant, a bearer-protected Group Life B2B integration estate (glsb2b), per-distributor API hosts including one named for the Iress adviser software, and a production Underwriting Rules Engine GraphQL endpoint — none of which is documented, registrable or self-serve. There is no developer portal, no public API reference, no downloadable OpenAPI, and no published ACORD or AL3 position. Australia's Consumer Data Right was designated to extend to insurance but was deferred, so no open-insurance mandate forces a public surface here.

**Areas:** Insurance · Australia · Life Insurance · Income Protection · Group Insurance · Superannuation · Underwriting · Claims · Carrier · Embedded Insurance · GraphQL · Identity

## TAL on APIs.io

Everything profiled for TAL is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/tal-australia/](https://apis.io/providers/tal-australia/)** — or go straight to one of the APIs or properties below.

### APIs (3)

- [TAL Partner Identity](https://apis.io/apis/tal-australia/tal-partner-identity/) — TAL's partner-facing OpenID Connect identity tenant (Okta org talpartner-au.okta.com), and the only machine-readable API contract TAL serves anonymously.…
- [TAL Group Life B2B (glsb2b)](https://apis.io/apis/tal-australia/tal-group-life-b2b-glsb2b/) — The integration estate behind TAL's group insurance business with superannuation funds — underwriting in/out (uwin, uwout), claims in/out (claimsin,…
- [TAL Underwriting Rules Engine (URE) GraphQL](https://apis.io/apis/tal-australia/tal-underwriting-rules-engine-ure-graphql/) — A live production GraphQL endpoint serving TAL's Underwriting Rules Engine. It answers anonymous POSTs and reports a query root type of CaseQuery with no…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Tal Australia Authentication](https://apis.io/security/tal-australia/tal-australia-authentication/)
- [Tal Australia Domain Security](https://apis.io/security/tal-australia/tal-australia-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Tal Australia Scopes](https://apis.io/scopes/tal-australia/tal-australia-scopes/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.tal.com.au/)
- [Support](https://www.tal.com.au/contact-us)
- [Blog](https://www.tal.com.au/slice-of-life-blog)
- [Security](https://www.tal.com.au/security)
- [Privacy policy](https://www.tal.com.au/privacy-policy)

## API Evangelist rating

**Kin Score 19.6** — emerging · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 79.5 |
| Contract quality | 0.0 |
| Contract governance | 4.5 |
| Operational transparency | 10.5 |
| Developer ergonomics | 19.0 |
| Access clarity | 17.1 |

**Agent readiness 15.8** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | — |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |

**Regulatory alignment 33.3** — Insurance

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/tal-australia/](https://apis.io/providers/tal-australia/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for TAL: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/tal-australia/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
