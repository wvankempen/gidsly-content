# gidsly-content

Public, editable source of truth for Gidsly's legal copy.

## What lives here

- `privacy.md` — Privacy Notice, served at `app.gidsly.com/privacy` and `www.gidsly.com/privacy`
- `terms.md` — Terms of Service, served at `app.gidsly.com/terms` and `www.gidsly.com/terms`

Both files are pure markdown. They are fetched at runtime by both the
Gidsly app and the Gidsly marketing site via jsDelivr's CDN, which
serves any public GitHub file at:

```
https://cdn.jsdelivr.net/gh/wvankempen/gidsly-content@main/<filename>
```

## How to edit

1. Open the file you want to change directly on GitHub
2. Click the pencil icon (top-right of the file view)
3. Make your edit
4. Scroll down, click "Commit changes" with a brief description

That's it. Within ~12 hours (jsDelivr cache TTL) the change is live on
both surfaces. To force an instant refresh while testing, append a
cache-buster query parameter to the URL or use jsDelivr's purge endpoint.

## What does NOT belong here

- Drafts or work-in-progress wording. Edit on a branch instead, or
  iterate in a Notion doc and only land the final version here.
- Internal notes, TODOs, "remove before publishing" markers. Anything
  in this repo is public the moment it lands on `main`.
- Anything not directly displayed to users. Operational documentation
  about how Gidsly works internally lives in the main app repo, not here.

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

## What this repo replaces

Before this repo existed, the legal markdown lived in the main app
repo (`docs/privacy-notice.md` and `docs/terms-of-service.md`) and was
either bundled into the app at build time (Vite `?raw` import) or
processed through a `build:marketing-legal` script that generated
static HTML in the marketing site repo. Every legal copy change
required two deploys (app + marketing) and depended on the EB
deploy pipeline being healthy.

By moving content here and serving via jsDelivr, content edits no
longer require any deploy at all. Code changes still go through the
normal app and marketing site pipelines.

## Owner

Van Kempen Ventures and Consultancy (KvK 42055010), Netherlands.
For questions: info@gidsly.com.
