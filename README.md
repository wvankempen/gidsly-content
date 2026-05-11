# gidsly-content

Public, editable source of truth for Gidsly's legal copy.

## What lives here

- `privacy.md` — Privacy Notice, served at `www.gidsly.com/privacy` and `app.gidsly.com/privacy`
- `terms.md` — Terms of Service, served at `www.gidsly.com/terms` and `app.gidsly.com/terms`
- `subprocessors.md` — List of third-party vendors that process personal data on Gidsly's behalf, served at `www.gidsly.com/subprocessors`

All three are pure markdown. They are fetched at runtime by the
Gidsly marketing site (and eventually the app) directly from raw
GitHub:

```
https://raw.githubusercontent.com/wvankempen/gidsly-content/main/<filename>
```

## How to edit

1. Open the file you want to change directly on GitHub
2. Click the pencil icon (top-right of the file view)
3. Make your edit
4. Scroll down, click "Commit changes" with a brief description
5. Select "Commit directly to the main branch"
6. Click the green "Commit changes" button

Within a few minutes (raw GitHub's short cache + browser revalidation)
the change is live on every surface that fetches it. No deploys
needed. No manual cache purges.

## What does NOT belong here

- Drafts or work-in-progress wording. Edit on a branch instead, or
  iterate in a Notion doc and only land the final version here.
- Internal notes, TODOs, "remove before publishing" markers. Anything
  in this repo is public the moment it lands on `main`.
- Anything not directly displayed to users. Operational documentation
  about how Gidsly works internally lives in the main app repo, not
  here. The internal data map and incident-response procedure stay
  internal; the privacy notice references them by description, not by
  link.

## Editing principles

- **Plain language first.** Both pages are read by people figuring out
  if they trust Gidsly with their data. Lawyer-clean phrasing is fine
  where required, but lead with what an actual person would understand.
- **No em dashes** (—). Use a comma, period, colon, or a connector
  word like "and", "but", "because". Same rule across all Gidsly
  surfaces (app, marketing, this repo).
- **Markdown only.** No HTML inside the markdown — both surfaces
  render the markdown through identical parsers and HTML can break
  the layout one but not the other.
- **Headings start at H2** for sections inside the document. The H1
  at the top is the document title and there should be exactly one
  per file.
- **Links to other pages in this repo** should use the public URL
  (e.g. `[Privacy Notice](https://gidsly.com/privacy)`), not the
  relative `.md` path. Otherwise the link breaks when rendered on
  the website.

## How updates propagate

1. You commit a change to `main` on github.com.
2. Within ~5 minutes, raw GitHub serves the new file (their CDN cache
   refreshes naturally).
3. The marketing site (`www.gidsly.com/*`) fetches with
   `cache: 'no-cache'` so it always revalidates with raw GitHub on
   every page load. Once raw GitHub has the new file, the next visitor
   sees it immediately.
4. The very first edit after a long gap can take ~10 min while the
   raw GitHub edge cache warms up. Edits after that propagate within
   the few-minute window.

## What this repo replaces

Before this repo existed, the legal markdown lived in the main app
repo (`docs/privacy-notice.md` and `docs/terms-of-service.md`) and was
either bundled into the app at build time (Vite `?raw` import) or
processed through a `build:marketing-legal` script that generated
static HTML in the marketing site repo. Every legal copy change
required two deploys (app + marketing) and depended on the EB
deploy pipeline being healthy.

By moving content here and serving via raw GitHub, content edits no
longer require any deploy at all. Code changes still go through the
normal app and marketing site pipelines.

## Owner

Van Kempen Ventures and Consultancy (KvK 42055010), Netherlands.
For questions: info@gidsly.com.
