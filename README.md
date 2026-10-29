# Churnkey

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

Churnkey is retention and growth infrastructure for subscription companies. It provides personalized Cancel Flows that intercept subscription cancellations with pauses, discounts, plan changes and surveys; Failed Payment Recovery (dunning) that recovers involuntary churn; and Reactivation campaigns that win back churned customers. Churnkey embeds via a JavaScript SDK authenticated with a server-computed HMAC authHash, and exposes REST APIs for session/analytics data, event tracking, customer updates, billing-contact management, and GDPR data-subject requests, plus signed webhooks. It integrates with Stripe, Chargebee, Paddle, Braintree, and Maxio.

**Areas:** Churn Prevention · Retention · Cancellation Flows · Failed Payment Recovery · Dunning · Reactivation · Subscription · Software-as-a-Service

## Churnkey on APIs.io

Everything profiled for Churnkey is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/churnkey/](https://apis.io/providers/churnkey/)** — or go straight to one of the APIs or properties below.

### APIs (7)

- [Churnkey Cancel Flow Embed](https://apis.io/apis/churnkey/churnkey-cancel-flow-embed/) — Client-side embed surface for personalized Cancel Flows. The JavaScript SDK is initialized with window.churnkey.init(), passing an appId, customerId,…
- [Churnkey Reactivation API](https://apis.io/apis/churnkey/churnkey-reactivation-api/) — Reactivation (win-back) campaigns that re-engage churned or paused customers with targeted offers. Reactivations are a documented Churnkey product, but a…
- [Churnkey Billing Contacts API](https://apis.io/apis/churnkey/churnkey-billing-contacts-api/) — Billing-contact management for Failed Payment Recovery.
- [Churnkey Customers API](https://apis.io/apis/churnkey/churnkey-customers-api/) — Customer and B2B user attribute updates.
- [Churnkey Data Subject Requests API](https://apis.io/apis/churnkey/churnkey-data-subject-requests-api/) — GDPR access and deletion requests (Data API).
- [Churnkey Events API](https://apis.io/apis/churnkey/churnkey-events-api/) — Customer event tracking and passive data enrichment.
- [Churnkey Sessions API](https://apis.io/apis/churnkey/churnkey-sessions-api/) — Cancel Flow session data and aggregations (Data API).

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [churnkey](https://apis.io/servers/churnkey/churnkey/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Churnkey Agentic Access](https://apis.io/agentic-access/churnkey/churnkey-agentic-access/)

#### Collections (6)

Postman and Open Collection request collections.

- [Churnkey API](https://apis.io/collections/churnkey/open-churnkey/)
- [Churnkey Billing Contacts API](https://apis.io/collections/churnkey/open-churnkey-billing-contacts-api/)
- [Churnkey Billing Contacts Customers API](https://apis.io/collections/churnkey/open-churnkey-customers-api/)
- [Churnkey Billing Contacts Data Subject Requests API](https://apis.io/collections/churnkey/open-churnkey-data-subject-requests-api/)
- [Churnkey Billing Contacts Events API](https://apis.io/collections/churnkey/open-churnkey-events-api/)
- [Churnkey Billing Contacts Sessions API](https://apis.io/collections/churnkey/open-churnkey-sessions-api/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Churnkey Authentication](https://apis.io/security/churnkey/churnkey-authentication/)
- [Churnkey Domain Security](https://apis.io/security/churnkey/churnkey-domain-security/)
- [Churnkey Trust Center](https://apis.io/security/churnkey/churnkey-trust-center/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Churnkey Plans Pricing](https://apis.io/plans/churnkey/churnkey-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Churnkey Rate Limits](https://apis.io/rate-limits/churnkey/churnkey-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Churnkey Finops](https://apis.io/finops/churnkey/churnkey-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://churnkey.co)
- [Documentation](https://docs.churnkey.co)
- [Pricing](https://churnkey.co/pricing)
- [Blog](https://churnkey.co/blog)
- [GitHub](https://github.com/churnkey)

## API Evangelist rating

**Kin Score 27.2** — thin · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 68.3 |
| Contract quality | 40.2 |
| Contract governance | 0.0 |
| Operational transparency | 10.5 |
| Developer ergonomics | 25.0 |
| Access clarity | 26.3 |

**Agent readiness 45.8** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | verified |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | distinct |

**Regulatory alignment 15.2** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/churnkey/](https://apis.io/providers/churnkey/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Churnkey: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/churnkey/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
