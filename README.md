# Churnkey (churnkey)

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
