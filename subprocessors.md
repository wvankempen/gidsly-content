# Subprocessors

GDPR Article 28 requires the controller to disclose which third-party
services (the **processors** and **sub-processors**) handle personal data
on its behalf. Users of Gidsly, prospective customers, and regulators
are entitled to see this list.

The controller is **Van Kempen Ventures and Consultancy** (eenmanszaak,
registered in the Netherlands, KvK 42055010). Gidsly is a registered
tradename of that entity.

## Active subprocessors

| # | Vendor | Purpose | Personal data transferred | Host region | Terms |
|---|---|---|---|---|---|
| 1 | **Render Services Inc.** | Hosting for the backend application server (`api.gidsly.com`) and managed PostgreSQL database. The entire production application stack runs here. | All persisted user data: profile, applications, documents, sessions, vacancy text, contacts. | Frankfurt, Germany (EU) | [Render DPA](https://render.com/legal/dpa) |
| 2 | **Cloudflare, Inc.** | DNS for `gidsly.com`, `app.gidsly.com`, and `api.gidsly.com`. Cloudflare Pages serves the Gidsly application frontend at `app.gidsly.com` (static JavaScript and HTML, no user data stored). Edge caching in front of the marketing site. | Visitor IP and user-agent in access logs. No application or account data passes through Cloudflare for the backend (the `api.gidsly.com` record is DNS-only, not proxied). | Global edge network with EU origin priority for `app.gidsly.com` and the marketing site | [Cloudflare DPA](https://www.cloudflare.com/cloudflare-customer-dpa/) |
| 3 | **Anthropic** | LLM processing: powers document tailoring, onboarding extraction, coaching conversations. | Prompts may contain profile content, CV text, vacancy text, conversation transcripts. Not retained on Anthropic's side per their API policy (zero-retention API). | United States | [Anthropic DPA](https://www.anthropic.com/legal/dpa) |
| 4 | **Zitadel Cloud** | Authentication and identity provider (login, magic-link, MFA). | Email, first and last name, MFA secrets, session tokens. | EU region (Germany) | [Zitadel DPA](https://zitadel.com/docs/legal/policies/data-processing-agreement) |
| 5 | **Brevo** | Transactional email (auth codes, magic links, password reset, MFA codes), marketing list storage, live chat widget. | Email address, first and last name, generated codes for transactional mail. Chat transcripts plus IP and user-agent for the support chat. | France (EU) | [Brevo DPA](https://www.brevo.com/legal/dpa/) |
| 6 | **Nylas** | Email and calendar integration: reads the user's inbox, threads, calendars, contacts on the user's explicit behalf. | Whatever the user has in their connected email or calendar. Gidsly does not build a permanent shadow copy. | United States | [Nylas DPA](https://www.nylas.com/terms-policies/data-processing-addendum/) |
| 7 | **GitHub** | Hosts the public legal-content repository (`gidsly-content`) which serves this notice and the Privacy Notice and Terms of Service to user browsers via `raw.githubusercontent.com`. | Visitor IP and user-agent when the legal pages are loaded. No application data. | United States (Microsoft) | [GitHub DPA](https://docs.github.com/en/site-policy/privacy-policies/global-privacy-practices) |
| 8 | **Google Fonts** | Serves the Inter, Fraunces, and Libre Baskerville typefaces used by the marketing site at `gidsly.com`. | Visitor IP and user-agent when the fonts load. | United States | [Google DPA](https://workspace.google.com/terms/dpa_terms.html) |
| 9 | **Sentry** | Error tracking: captures unhandled errors and exceptions from both the backend (`api.gidsly.com`) and the React frontend running in users' browsers (`app.gidsly.com`). Helps us notice and fix bugs that affect users. | Error stack traces, error messages, URL where the error occurred, browser type, and any application context attached to the error. We do not deliberately send user IDs or email addresses; however, error messages may incidentally contain such data if it appears in an exception thrown by the application. Browser-side: client IP is recorded by Sentry by default; we have explicitly disabled enriched-PII capture (`sendDefaultPii: false`). | Germany (EU region; `*.ingest.de.sentry.io`) | [Sentry DPA](https://sentry.io/legal/dpa/) |
| 10 | **LinkedIn (Microsoft Ireland Operations Ltd)** | Optional profile-data import via the DMA Member Data Portability API. User-initiated, OAuth-consented (scope `r_dma_portability_3rd_party`). Used at two surfaces: (a) onboarding — pulls the user's own profile to pre-fill their Essence; (b) when the user creates a new journey, surfaces their LinkedIn connections who work at the company being added, so they can pick which to add as stakeholders. | Profile fields received from LinkedIn: name, headline, summary, location, address, postal code, positions (career timeline), education, skills, certifications, languages. Connections received: name, current company, position, profile URL (only the user's own connections, only used to suggest stakeholders at companies the user is actively pursuing). OAuth access + refresh tokens are stored encrypted at rest in our Postgres (`linkedin_authorizations` table, pgcrypto `pgp_sym_encrypt`). Cached snapshot stored per user (`linkedin_snapshots`, `linkedin_connections_cache` with 7-day TTL). All deleted on user account erasure (FK CASCADE) and on explicit LinkedIn disconnect from Settings. | Microsoft / Ireland | [LinkedIn DPA](https://www.linkedin.com/legal/l/dpa) |
| 11 | **PostHog Inc.** | Product analytics and session replay. Helps us understand how users move through the product and debug user-experience issues. | Page views, click events, named milestone events (`user_signed_in`, `onboarding_started`, `onboarding_method_selected`, `linkedin_connected`, `linkedin_imported`, `onboarding_completed`, `application_created`, `contact_created`, `linkedin_contacts_suggested`, `linkedin_contacts_imported_at_company`, `document_tailored`). Identified-user fields: user id, email, first and last name, onboarded flag. Session recordings with default PII masking: all `<input>` elements and any element tagged `.ph-no-capture` are masked in the replay. Do-Not-Track headers are honoured. | EU region (`eu.i.posthog.com`), reached via a same-origin reverse proxy at `app.gidsly.com/ph/*` | [PostHog DPA](https://posthog.com/dpa) |
| 12 | **Mollie B.V.** | Payment processing for Premium subscriptions. Handles hosted checkout (card, iDEAL, Bancontact, Sofort, SEPA Direct Debit, Apple Pay, Google Pay), mandate capture for recurring charges, the monthly or annual billing cycle, refunds, and chargebacks. | Email address, first and last name, the user's chosen plan and interval, and a `gidsly_user_id` reference used to mirror state back to our database. **Card and bank account details never reach Gidsly**: they are entered on Mollie's hosted checkout page and stored on Mollie's infrastructure. Subscription state changes (created, paid, past_due, canceled, expired) are pushed back to Gidsly via webhook. Mollie sends transactional emails (receipts, mandate confirmations) directly to the user under its own privacy notice. | Netherlands (Amsterdam) | [Mollie DPA](https://www.mollie.com/legal/data-processing-agreement) |

## Planned subprocessors

_(None at present. New vendors will be listed here before they receive production traffic.)_

## Out-of-scope tools (not subprocessors)

Vendors used internally that do not process personal data on Gidsly's
behalf and therefore do not appear on the subprocessor list:

- **GitHub** (private app and marketing repos): source-code hosting. No
  personal data about Gidsly users. (Only the public `gidsly-content`
  repo touches user-facing requests, see #8 above.)
- **npm registry**: dependency source.
- **Development tooling**: local IDE, build toolchain, test runners.

## When this page is updated

- A new vendor starts processing personal data: a new row is added
  before production traffic reaches them.
- A vendor's scope changes: the "Personal data transferred" column is
  updated.
- A vendor is retired: the row moves to the Historical section below
  with the end date.
- Any change here is a material change to the privacy notice; users are
  notified.

## Historical

Vendors previously used to process Gidsly user data. Kept for audit
and Data Subject Request fulfilment.

| Vendor | Period | Reason for replacement |
|---|---|---|
| **ElevenLabs** | Pre-2026-05-28 | Powered text-to-speech for Gidsly's spoken responses in the original chat-style onboarding flow. The chat onboarding was retired on 2026-05-28 (replaced by the LinkedIn-import-and-review flow), removing the only caller of the TTS endpoints. Both the vendor integration and the relevant proxy endpoints (`/api/tts`, `/api/elevenlabs-tts`, `/api/elevenlabs-token`) were removed in the same change. No user data was retained by ElevenLabs (text strings only, no microphone audio). |
| **Amazon Web Services (AWS)** | 2026-04 to 2026-05-18 | Hosted the application backend (Elastic Beanstalk) and database (RDS PostgreSQL) in the Ireland (`eu-west-1`) region. Migrated to Render (Frankfurt) on 2026-05-18 after a series of platform-level deploy-stability incidents on EB made it unsuitable for production at Gidsly's scale. All user data was migrated and the AWS environment was decommissioned with a final snapshot retained. |
| **Vercel** | Pre-2026-04 | Original hosting provider. Migrated to AWS Elastic Beanstalk in April 2026 for EU-residency control and to consolidate compute and database with one provider. (AWS itself was subsequently replaced by Render in May 2026 — see row above.) |
