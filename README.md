# Churnkey (churnkey)

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

Churnkey is retention and growth infrastructure for subscription companies. It provides personalized **Cancel Flows** that intercept subscription cancellations with pauses, discounts, plan changes, and surveys; **Failed Payment Recovery** (dunning) that recovers involuntary churn; and **Reactivation** campaigns that win back churned customers. Churnkey embeds via a JavaScript SDK authorized with a server-computed HMAC `authHash`, and exposes REST APIs for session/analytics data, event tracking, customer updates, billing-contact management, and GDPR data-subject requests, plus signed webhooks. It integrates with Stripe, Chargebee, Paddle, Braintree, and Maxio.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/churnkey/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/churnkey/refs/heads/main/apis.yml)

## Access Model

Churnkey's documentation is public and self-serve at [docs.churnkey.co](https://docs.churnkey.co). Using the APIs requires a paid Churnkey subscription, but credentials are self-provisioned from the dashboard: an **App ID** (`x-ck-app`), a **Cancel Flow API key** (used to compute the embed `authHash`), and a separate **Data API key** (`x-ck-api-key`) found under Settings > Account. The docs note you can also email Churnkey to enable Data API access for your organization. All REST endpoints below are documented in the public reference; the Cancel Flow UI is delivered client-side via the JS SDK and is not a REST resource API. The Reactivation product is documented but does not publish a dedicated public REST endpoint set, so its API is honestly modeled rather than confirmed.

## Tags

- Churn Prevention
- Retention
- Cancellation Flows
- Failed Payment Recovery
- Dunning
- Reactivation
- Subscriptions
- SaaS

## Timestamps

- **Created:** 2026-07-10
- **Modified:** 2026-07-10

## APIs

### Churnkey Data API

Query Cancel Flow session data programmatically. List sessions with rich filters (customer, plan, blueprint, A/B test, offer type, save type, coupon, date range) and retrieve grouped/aggregated session counts. Authenticated with a Data API key and App ID headers, distinct from the Cancel Flow API key.

- **Human URL:** [https://docs.churnkey.co/data-api](https://docs.churnkey.co/data-api)
- **Base URL:** `https://api.churnkey.co/v1/data`
- Confirmed REST: `GET /sessions`, `GET /session-aggregation`

### Churnkey Event Tracking API

Send customer events into Churnkey to enrich segmentation, targeting, and passive data collection. Create single events, bulk events (up to 100 per request), and update customer or B2B user attributes.

- **Human URL:** [https://docs.churnkey.co/data-integrations/event-tracking/](https://docs.churnkey.co/data-integrations/event-tracking/)
- **Base URL:** `https://api.churnkey.co/v1/api`
- Confirmed REST: `POST /events/new`, `POST /events/bulk`, `POST /events/customer-update`

### Churnkey Billing Contact API

Configure the billing contacts that receive Failed Payment Recovery (dunning) communications. Attach one or more users to a customer and flag which are billing admins, improving recovery rates for team accounts. Supports single and bulk updates.

- **Human URL:** [https://docs.churnkey.co/failed-payment-recovery/billing-contact-api/](https://docs.churnkey.co/failed-payment-recovery/billing-contact-api/)
- **Base URL:** `https://api.churnkey.co/v1/api`
- Confirmed REST: `POST /events/customer-update/set-users`, `POST /events/customer-update/set-users/bulk`

### Churnkey Data Subject Requests API

GDPR data-subject request endpoints for retrieving or deleting all personal data Churnkey has stored for a user, identified by email.

- **Human URL:** [https://docs.churnkey.co/data-api](https://docs.churnkey.co/data-api)
- **Base URL:** `https://api.churnkey.co/v1/data`
- Confirmed REST: `POST /dsr/access`, `POST /dsr/delete`

### Churnkey Cancel Flow Embed

Client-side embed surface for personalized Cancel Flows. The JavaScript SDK is initialized with `window.churnkey.init()`, passing an `appId`, `customerId`, `subscriptionId`, `provider`, and a server-computed HMAC-SHA256 `authHash` (the customer ID signed with the Cancel Flow API key). This is a client SDK plus HMAC authorization surface, not a REST resource API.

- **Human URL:** [https://docs.churnkey.co/installing-churnkey](https://docs.churnkey.co/installing-churnkey)

### Churnkey Reactivation API

Reactivation (win-back) campaigns that re-engage churned or paused customers with targeted offers. Reactivations are a documented product, but a dedicated public REST endpoint set is not published; campaigns are configured in the dashboard and driven by the same customer/event data surfaced through the Event Tracking and Data APIs. **Endpoints modeled, not confirmed.**

- **Human URL:** [https://churnkey.co/feature/reactivations](https://churnkey.co/feature/reactivations)

## Authentication

- **REST APIs** — `x-ck-api-key` (Data API key or Churnkey API key) plus `x-ck-app` (App ID) headers.
- **Cancel Flow embed** — HMAC-SHA256 `authHash` of the customer ID signed with the Cancel Flow API key, computed server-side.
- **Webhooks** — signed with the organization `webhookSecret` and verified via the `ck-signature` (SHA-256 HMAC) header.

## Common Properties

- [GitHub Organization](https://github.com/churnkey)
- [LinkedIn](https://www.linkedin.com/company/churnkey)
- [Website](https://churnkey.co)
- [Documentation](https://docs.churnkey.co)
- [Plans](plans/churnkey-plans-pricing.yml)
- [Rate Limits](rate-limits/churnkey-rate-limits.yml)
- [Fin Ops](finops/churnkey-finops.yml)
- [Pricing](https://churnkey.co/pricing)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
