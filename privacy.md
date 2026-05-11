# Privacy Notice

## 1. Who is responsible for your data?

**Gidsly** is a registered tradename of **Van Kempen Ventures and Consultancy**, registered in the Netherlands. TEST1234
**Van Kempen Ventures and Consultancy** is a sole proprietorship under Dutch law, so Gidsly is operated
by a natural person, not a limited-liability company.

- **Registered address:** Fort Abcoudestraat 12, 1384 AJ Weesp, Netherlands
- **KvK (Chamber of Commerce) number:** **42055010**

If you want to reach us about your data or this notice:

- **Email:** privacy@gidsly.com

We are the **data controller** for the personal data described in this notice.
Any vendor helping us process your data (our **sub-processors**) is listed in
[subprocessors.md](subprocessors.md).

## 2. What is Gidsly?

Gidsly is a career companion app. It helps you track job applications, tailor
your CV and cover letters, practise interviews, and manage the emotional side
of a career transition. Everything below is how we handle the data you give us
while using it.

## 3. What personal data we collect

We collect only what we need to run the service. The complete reference is in
our internal [data map](data-map.md); the summary here is what you give us
directly:

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
- **Voice input.** If you speak to Gidsly, your speech is converted to text
  immediately and the **raw audio is discarded**. We never retain audio
  recordings.

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
- **Errors**, via our error-tracking subprocessor, to fix bugs.

### 3.6 When you chat with us

A chat widget is available to signed-in users. If you message us, the
transcript (whatever you type), your IP address, and your browser are
processed by **Brevo Conversations** on our behalf and stored on
Brevo's EU-resident infrastructure so we can read and reply. We use
these transcripts only to respond to you and to improve the product.
The widget does not load on logged-out pages.

### 3.7 When you import your LinkedIn profile (optional)

If you choose to import your LinkedIn profile into your Gidsly
Essence, we ask **LinkedIn** for a copy of your own profile data on
your behalf, using LinkedIn's Member Data Portability API under the
EU Digital Markets Act.

What we receive: headline, summary, work experience, education,
skills, certifications, and languages. We do **not** receive your
connections, messages, posts, endorsements, or recommendations.

What we do with it: show you a preview, let you edit anything, and
save the result into your Essence as your own editable content. The
LinkedIn access token we use to fetch the data is held in memory for
the duration of the import only and is never stored.

This import is entirely optional; you can build your Essence
manually and never connect LinkedIn. If you do connect and later
change your mind, the imported data becomes your Essence content
and can be edited or deleted at any time like everything else.

### 3.8 What we do NOT collect

- No tracking cookies beyond what's needed to run the site.
- No advertising pixels.
- No selling of data to third parties, ever.
- No social-graph data beyond the contacts you explicitly add.

## 4. Why we process your data, and on what legal basis

| Purpose | Legal basis (GDPR Art. 6) |
|---|---|
| Providing the service you signed up for (storing your profile, applications, etc.) | Performance of a contract |
| Keeping the service secure and preventing abuse | Legitimate interest |
| Sending service-related messages (password resets, security alerts) | Performance of a contract |
| Sending marketing emails (when and if we offer them) | **Consent**: opt-in only; always optional |
| Complying with legal obligations (tax records, incident reporting) | Legal obligation |
| Improving Gidsly (aggregated analytics, anonymised feedback) | Legitimate interest |

We do not process **special category data** (as defined by GDPR Art. 9).
The product deliberately avoids collecting it.

## 5. Who we share your data with

We share personal data only with the sub-processors listed in
[subprocessors.md](subprocessors.md), and only to the extent they need to
provide their service to us. In plain language, those are:

- **Anthropic**, runs the AI that powers document tailoring and coaching.
- **ElevenLabs**, generates the synthetic voice for Gidsly's spoken
  responses.
- **Nylas**, provides the connection to your email and calendar, when you
  connect one.
- **Vercel**, hosts the Gidsly web app.
- **Google Fonts**, serves the font the UI uses.

After May 2026 we expect to add **AWS** (for EU-based cloud hosting) and
a dedicated authentication provider. We'll update this section before
those vendors start processing data.

We do **not** sell your data, and we never share it with advertisers or
data brokers.

## 6. Where your data is processed

The Gidsly team is based in the Netherlands. Our production data storage
will be in **Frankfurt, Germany** (EU region) once AWS is in place.

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
| Voice input | Raw audio is discarded immediately after transcription. |
| Email content cached from Nylas | About an hour, then discarded. |
| Error logs | 90 days. |
| Audit logs (security events about your account) | Deleted together with your account. |
| Consent records | Kept while the account is active, and for the legally required period afterwards to prove we obtained valid consent. |

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
- If a breach ever happens, we follow the procedure in
  [incident-response.md](incident-response.md); where legally required
  we'll notify you within 72 hours.

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
privacy@gidsly.com

---
