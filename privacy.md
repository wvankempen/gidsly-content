# Privacy Notice

## 1. Who is responsible for your data?

**Gidsly** is a registered tradename of the eenmanszaak
**Van Kempen Ventures and Consultancy**, registered in the Netherlands.
An eenmanszaak is a sole proprietorship under Dutch law, so Gidsly is operated
by a natural person, not a limited-liability company.

- **Registered address:** Fort Abcoudestraat 12, 1384 AJ Weesp, Netherlands
- **KvK (Chamber of Commerce) number:** **42055010**

If you want to reach us about your data or this notice:

- **Email:** info@gidsly.com

We are the **data controller** for the personal data described in this notice.
Any vendor helping us process your data (our **sub-processors**) is listed at
[gidsly.com/subprocessors](https://gidsly.com/subprocessors).

## 2. What is Gidsly?

Gidsly is a career companion app. It helps you track job applications, tailor
your CV and cover letters, practise interviews, and manage the emotional side
of a career transition. Everything below is how we handle the data you give us
while using it.

## 3. What personal data we collect

We collect only what we need to run the service. We maintain an internal data
map for our own audit purposes; the summary here is what you give us directly:

### 3.1 When you create an account

- **First name, last name, email address.** Required for an account.
- **Password.** Stored as a cryptographic hash; we never see your actual
  password.
- **Phone number.** **Optional.** If you provide it we may use it later for
  multi-factor authentication; never for marketing.

### 3.2 When you build your profile

- **Career context:** job title, current company, experience level, career
  goals, work preferences, salary expectations.
- **Education, work history, skills, certifications, projects, languages.**
- **Address.** So we can match you to roles in the right region.
- **Age bracket** (optional; e.g. "35–44"). We do **not** collect your exact
  date of birth.
- **Pronouns** (optional).

We do **not** collect: ethnicity, sex, disability status, veteran status. We
removed these in April 2026 because they weren't essential to the service.

### 3.3 When you use Gidsly

- **Job applications you add**, including company, role, dates, status, notes.
- **Documents you upload** (CVs, cover letters, job postings).
- **Contacts you explicitly link** to an application (recruiters, referrers).
  We do **not** auto-import your whole address book.
- **Conversations** you have with Gidsly's AI features (document tailoring,
  coaching, wellness support), stored as text.

### 3.4 When you connect an email or calendar

If you choose to connect your email / calendar via **Nylas**:

- We access the threads, messages and contacts needed for the features you
  use. We do **not** build a permanent copy of your inbox; email content is
  cached briefly (about an hour) then discarded.
- You can disconnect at any time from your account settings.

### 3.5 Automatically

- **Basic technical data** to operate the service: IP address, browser,
  device type, pages visited, times of action. Used for security and
  debugging.
- **Errors**, logged to our infrastructure for debugging.
- **Product analytics and session recordings** via **PostHog**
  (EU-hosted). We capture page views, click events, and a defined list
  of named milestone events (such as "signed in", "onboarding
  completed", "application created") tied to your account so we can
  understand how the product is actually used and fix UX problems.
  Session recordings replay your screen interactions (clicks, scrolls,
  form fills) with privacy masking: every `<input>` field and any
  element we explicitly mark as sensitive are masked in the playback,
  so passwords and free-text personal answers are not visible in
  replays. We honour the **Do-Not-Track** browser signal — if your
  browser sends it, PostHog does not start. You can also email us
  (see §1) to ask us to disable session recordings for your account
  going forward. Analytics requests are routed through
  `app.gidsly.com/ph/*` (a reverse proxy on our own infrastructure)
  before reaching PostHog's EU servers. This makes the request appear
  first-party so that browser ad blockers do not silently drop it; the
  data, the recipient and the DPA remain unchanged.

### 3.6 When you chat with us

A chat widget is available to signed-in users. If you message us, the
transcript (whatever you type), your IP address, and your browser are
processed by **Brevo Conversations** on our behalf and stored on
Brevo's EU-resident infrastructure so we can read and reply. We use
these transcripts only to respond to you and to improve the product.
The widget does not load on logged-out pages.

### 3.7 When you import your LinkedIn profile (optional)

If you choose to connect LinkedIn from onboarding or from your
Account Settings, we use **LinkedIn**'s Member Data Portability API
under the EU Digital Markets Act to pull a copy of your own profile
on your behalf.

**What we receive from LinkedIn:**

- *Always when you connect:* first name, last name, headline,
  professional summary, geographic location, full address, postal
  code, work experience (positions), education, skills,
  certifications, languages.
- *Only when you create a new journey at a specific company:* the
  subset of your LinkedIn connections who work at that company —
  name, current company, position, and profile URL. We surface them
  in the journey wizard so you can choose which to add as
  stakeholders for that journey. We do not pull or store anyone
  else's data.

**What we do with it:** we fill your Gidsly Essence (career profile)
using a "fill blanks only" rule — anything you've already typed
yourself stays exactly as you wrote it, and only empty fields get
filled from LinkedIn. You can review and edit every imported field
before completing onboarding, and at any time afterwards.

**About the access tokens:** to enable the re-sync and contact-
suggestion features, LinkedIn's OAuth access and refresh tokens are
stored **encrypted at rest** in our database (Render, Frankfurt),
using the PostgreSQL `pgcrypto` extension and a server-side key
that is not present in any backup or log. We never display the
tokens in the app.

**What we do NOT receive:** your messages, posts, endorsements,
recommendations, activity feed, or organisation/pages data.

**Disconnecting:** you can disconnect LinkedIn at any time from
**Account Settings → Connected Accounts**. Disconnect immediately
soft-deletes the OAuth row, revokes our ability to re-fetch, and
stops the contact-suggestion flow from looking at your network.
The profile data already in your Essence stays as your own editable
content; the cached snapshot stays for audit unless you also request
deletion via §8. Account deletion removes everything together.

### 3.8 When you subscribe to Premium

If you choose to subscribe to Gidsly Premium (or start the free
trial), payment is processed by **Mollie B.V.** in Amsterdam:

- **What Mollie receives:** your email address, first and last name,
  your chosen plan and interval (monthly or annual), and an internal
  Gidsly user reference so we can match the payment back to your
  account. Your card or bank-account details are entered on
  Mollie's hosted checkout page and live with Mollie. **Gidsly
  never sees and never stores your card number, IBAN, or any other
  payment instrument data.**
- **What we receive back from Mollie:** the subscription state
  (created, trialing, active, past_due, canceled, expired), the
  Mollie customer and subscription identifiers, and the amount and
  currency of each charge. We mirror this in our own database so
  the in-app Subscription view reflects your real billing state.
- **Receipts and mandate confirmations** are sent by Mollie directly
  to your email under Mollie's own privacy notice. Gidsly may also
  send you billing-related emails (trial ending in 3 days, payment
  failed, downgrade notice) via Brevo.
- **Cancellation, refunds, chargebacks** are processed by Mollie at
  our request and mirrored back to our database via the same
  webhook channel.
- We keep **billing records (invoices, payment receipts, subscription
  history)** for **7 years** because Dutch tax law (Article 52 AWR)
  requires it. This data survives account deletion: when you delete
  your account we erase your personal-data records but retain the
  billing line items in a tax-archive form for the required period.
  See §7 for the full retention table.

### 3.9 What we do NOT collect

- No tracking cookies beyond what's needed to run the site.
- No advertising pixels.
- No selling of data to third parties, ever.
- No social-graph data beyond the contacts you explicitly add.

## 4. Why we process your data, and on what legal basis

| Purpose | Legal basis (GDPR Art. 6) |
|---|---|
| Providing the service you signed up for (storing your profile, applications, etc.) | Performance of a contract |
| Processing a Premium subscription (charging, receipts, cancellation, refunds) | Performance of a contract |
| Keeping the service secure and preventing abuse | Legitimate interest |
| Sending service-related messages (password resets, security alerts, billing notices) | Performance of a contract |
| Sending marketing emails (when and if we offer them) | **Consent**: opt-in only; always optional |
| Keeping billing records for the required period | Legal obligation (Dutch tax law, 7 years) |
| Complying with other legal obligations (incident reporting, etc.) | Legal obligation |
| Improving Gidsly (aggregated analytics, anonymised feedback) | Legitimate interest |

We do not process **special category data** (as defined by GDPR Art. 9).
The product deliberately avoids collecting it.

## 5. Who we share your data with

We share personal data only with the sub-processors listed at
[gidsly.com/subprocessors](https://gidsly.com/subprocessors), and only to
the extent they need to provide their service to us. In plain language,
those are:

- **Render** (Frankfurt, Germany), hosts our application servers and
  database.
- **Cloudflare**, handles DNS, serves the Gidsly application at
  app.gidsly.com (the frontend code, not your data), and serves the
  marketing site at gidsly.com.
- **Anthropic**, runs the AI that powers document tailoring and coaching.
- **Zitadel** (EU), handles login and multi-factor authentication.
- **Brevo** (France), sends transactional email and runs the support chat.
- **Nylas**, provides the connection to your email and calendar, when you
  connect one.
- **LinkedIn** (Microsoft Ireland), source of the optional profile
  import and the company-specific connection suggestions in the
  journey wizard.
- **PostHog** (EU), receives product-analytics events and session
  recordings (with privacy masking) so we can understand product use
  and fix UX problems.
- **Sentry** (Germany), receives error reports if Gidsly hits an
  unexpected problem in your browser or our backend, so we can
  notice bugs and fix them. Error reports may contain technical
  details (the code path that failed, the URL you were on); we don't
  deliberately include your account data.
- **Mollie** (Amsterdam), processes payments for Premium subscriptions
  when you subscribe or upgrade. Card and bank-account details are
  entered on Mollie's hosted checkout page and stay with Mollie;
  Gidsly never sees them.
- **GitHub** and **Google Fonts**, serve the legal pages and the typefaces
  used on the marketing site.

We do **not** sell your data, and we never share it with advertisers or
data brokers.

## 6. Where your data is processed

The Gidsly team is based in the Netherlands. Our production data is stored
in **Germany** (Render, Frankfurt region).

Some subprocessors are based in the United States. Where that's the case,
we rely on the **EU–US Data Privacy Framework** and **Standard Contractual
Clauses** as the safeguard for transfers, and we prefer vendors who offer
EU-region processing.

## 7. How long we keep your data

| Category | Retention |
|---|---|
| Your account and profile | For as long as your account is active. Deleted ~30 days after you close it (grace period for accidental deletions), then permanently. |
| Job applications, todos, documents | Same as the account. |
| AI conversation history | Kept indefinitely by default; you can delete individual conversations at any time. |
| Email content cached from Nylas | About an hour, then discarded. |
| LinkedIn-cached connections (used for journey contact suggestions) | Refreshed weekly; older entries replaced on refresh. Removed entirely on LinkedIn disconnect or account deletion. |
| Product-analytics events (PostHog) | Per PostHog's default retention (currently up to 7 years for events). |
| Session recordings (PostHog) | Per PostHog's default retention (currently 1 month). |
| Error logs | 90 days. |
| Audit logs (security events about your account) | Deleted together with your account. |
| Consent records | Kept while the account is active, and for the legally required period afterwards to prove we obtained valid consent. |
| Billing records (invoices, payment receipts, subscription history) | **7 years** (Dutch tax law, Article 52 AWR). Retained in a tax-archive form even after account deletion. Personal-data fields beyond what tax law requires are minimised. |

## 8. Your rights

Under GDPR you have the right to:

- **Access**: ask for a copy of your personal data.
- **Rectification**: correct inaccurate data.
- **Erasure** ("right to be forgotten"): ask us to delete your account and
  your data.
- **Restriction**: ask us to stop using certain data.
- **Portability**: get your data in a structured, machine-readable format
  you can take elsewhere.
- **Object**: to processing based on legitimate interest.
- **Withdraw consent**: where we rely on consent (e.g. marketing emails).
- **Complain** to the Dutch supervisory authority (**Autoriteit
  Persoonsgegevens**, [autoriteitpersoonsgegevens.nl](https://autoriteitpersoonsgegevens.nl/))
  if you think we've mishandled your data.

You can exercise most of these rights directly in the app: _Account
Settings → Your Data_. For anything that doesn't have a button yet, email
us (see §1).

We'll respond within 30 days at the latest.

## 9. How we keep your data safe

- All data in transit is encrypted (HTTPS).
- Data at rest is encrypted in our database and file storage.
- Access to production data is limited to the founder today, and will be
  restricted via proper access controls as the team grows.
- We keep an internal audit log of access to personal data.
- If a breach ever happens, we follow our internal incident-response
  procedure; where legally required we'll notify you within 72 hours
  (per GDPR Article 33).

## 10. Children

Gidsly is not for children under 18. We ask you to confirm you are 18 or
older when you sign up. If we discover an account belongs to a child we'll
delete it.

## 11. Changes to this notice

We may update this notice when the product changes or when the law changes.
Material changes are communicated in the app, and we may ask you to
re-consent before you can keep using Gidsly. Every version is archived and
we can tell you which version you agreed to on which date.

## 12. Contact

Any question about this notice, your data, or our practices, reach us at
the contact in §1.

---
