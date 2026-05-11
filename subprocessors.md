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
| 1 | **Amazon Web Services (AWS)** | Hosting (Elastic Beanstalk), database (RDS Postgres), object storage. The entire production stack runs here. | All persisted user data: profile, applications, documents, sessions, vacancy text, contacts. | Ireland (`eu-west-1`) | [AWS DPA](https://aws.amazon.com/service-terms/) |
| 2 | **Cloudflare** | DNS for `gidsly.com` and `app.gidsly.com`; Cloudflare Pages serves the marketing site; edge caching in front of both. | Visitor IP + user-agent in access logs. No application data passes through. | Global edge network | [Cloudflare DPA](https://www.cloudflare.com/cloudflare-customer-dpa/) |
| 3 | **Anthropic** | LLM processing: powers document tailoring, onboarding extraction, coaching conversations. | Prompts may contain profile content, CV text, vacancy text, conversation transcripts. Not retained on Anthropic's side per their API policy (zero-retention API). | United States | [Anthropic DPA](https://www.anthropic.com/legal/dpa) |
| 4 | **Zitadel Cloud** | Authentication and identity provider (login, magic-link, MFA). | Email, first and last name, MFA secrets, session tokens. | EU region (Germany) | [Zitadel DPA](https://zitadel.com/docs/legal/policies/data-processing-agreement) |
| 5 | **Brevo** | Transactional email (auth codes, magic links, password reset, MFA codes), marketing list storage, live chat widget. | Email address, first and last name, generated codes for transactional mail. Chat transcripts plus IP and user-agent for the support chat. | France (EU) | [Brevo DPA](https://www.brevo.com/legal/dpa/) |
| 6 | **Nylas** | Email and calendar integration: reads the user's inbox, threads, calendars, contacts on the user's explicit behalf. | Whatever the user has in their connected email or calendar. Gidsly does not build a permanent shadow copy. | United States | [Nylas DPA](https://www.nylas.com/terms-policies/data-processing-addendum/) |
| 7 | **ElevenLabs** | Voice synthesis: text-to-speech for Gidsly's spoken responses. | Text strings sent for speech generation. Raw user microphone audio is not retained in Gidsly. | United States | [ElevenLabs DPA](https://elevenlabs.io/legal/dpa) |
| 8 | **GitHub** | Hosts the public legal-content repository (`gidsly-content`) which serves this notice and the Privacy Notice and Terms of Service to user browsers via `raw.githubusercontent.com`. | Visitor IP and user-agent when the legal pages are loaded. No application data. | United States (Microsoft) | [GitHub DPA](https://docs.github.com/en/site-policy/privacy-policies/global-privacy-practices) |
| 9 | **Google Fonts** | Serves the Inter, Fraunces, and Libre Baskerville typefaces used by the marketing site at `gidsly.com`. | Visitor IP and user-agent when the fonts load. | United States | [Google DPA](https://workspace.google.com/terms/dpa_terms.html) |

## Planned subprocessors

These are not yet active. They will move to the Active list before
production traffic reaches them.

| Vendor | Purpose | Status |
|---|---|---|
| **LinkedIn** (Microsoft Ireland) | Optional one-time import of the user's own LinkedIn profile data into their Gidsly Essence, via the DMA Member Data Portability API. User-initiated, OAuth-consented, no ongoing sync. Access tokens are not retained beyond the import session. | Developer-app approval pending |

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
| Hosting migrated to AWS Elastic Beanstalk for full EU-residency control and to consolidate compute, database, and storage with one EU-resident provider. |
