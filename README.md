# Breyes Agency — site

Single-file static site (`index.html`: inline CSS + JS, no build step). Deployed on Cloudflare Pages.

## Deploy

Push to `main` — Cloudflare Pages auto-deploys in 30-60 seconds. No build command; build output directory is the repo root (`/`).

## Update content

Edit `index.html` directly, commit, push. There is no compile step — this is a static HTML/CSS/JS export, not a Claude Design React/JSX export, so the usual JSX-compile pipeline doesn't apply here.

## Outstanding (not yet done)

- **Domain**: not registered yet. Canonical/OG/schema URLs in `index.html` and `robots.txt`/`sitemap.xml` currently point at `https://www.breyesagency.com` as a placeholder — update everywhere (grep for `breyesagency.com`) once a real domain is picked, whether or not it's that one.
- **Favicons + `site.webmanifest`**: skipped. No source logo/brand-mark image exists yet to generate the icon set from. Needs a 1024x1024 source image, then run through the standard favicon pipeline (SOP §10.3).
- **OG image**: skipped for the same reason — no 1200x630 social-preview image yet.
- **Tracking stack** (GA4, Meta Pixel, Microsoft Clarity): not wired in. No tracking IDs yet.
- **Booking**: CTA is a plain `mailto:` link by design for now, not Calendly.
- **Multi-page architecture**: intentionally still single-page. Real per-page URLs would help SEO/AEO further but is a real rebuild of the nav/scroll system — deferred.

## Conscious audit skips

- No `Content-Security-Policy` header yet (SOP anti-pattern: add only after auditing every script/style/connect endpoint the page actually uses).
- No `BreadcrumbList` schema — single-page site, no real breadcrumb trail.
