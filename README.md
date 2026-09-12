# baltsec

Static site for **baltsec.com** — served via GitHub Pages.
Primary language: **Lithuanian**. English version to follow under `/en/`.

## Structure

```
index.html          homepage (LT)
style.css           shared stylesheet (all pages link to it)
rasome/index.html   blog index (LT)
rasome/pradzia.html a post (LT)
CNAME               baltsec.com
robots.txt
```

No build step. No frameworks. No javascript. Edit an `.html` file, commit, push.

## Language policy

Lithuanian is the **main** version and lives at the root (`/`).
The English version will live at `/en/` and link back to `/` — build it only
after the Lithuanian copy is final, so the two do not drift.

## Publishing a post

1. Copy `rasome/pradzia.html` → `rasome/your-slug.html`
2. Edit the `<title>`, `<meta name="description">`, `<h1>`, and the `.eyebrow` date line
3. Write the body inside `<article class="post-page">` → `<div class="prose">`
4. Add a row to `rasome/index.html` **and** the `#rasome` section in `index.html`

Pre-styled article elements (see `style.css`): `h2`, `h3`, `p`, `ul`, `ol`,
`pre code`, `code`, `blockquote`, `table`, `strong`, `em`.

## Content rules

- **Legal claims must stay true.** The NIS2 / KSĮ section states what the law
  requires (audit at least once every 3 years, per NKSC methodology) and says
  plainly that the statutory audit is performed by certified auditors meeting
  KSĮ Art. 14(8). Do not imply baltsec is already such an auditor.
- **No invented facts.** No specific timelines, prices, client names, or
  certification claims unless actually held.
- Contact is `contact@baltsec.com` only.

## Paths

All internal links are **relative** (`style.css`, `../style.css`, `rasome/`),
never root-absolute. Root-absolute paths work on GitHub Pages but break local
`file://` preview, because `/` resolves to the drive root. Keep them relative.

## Deploy

1. Push to `main`
2. Repo → Settings → Pages → Source: `Deploy from a branch` → `main` / `/ (root)`
3. Add `baltsec.com` as custom domain, enable *Enforce HTTPS*

## DNS (at your registrar)

Four `A` records for the apex:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

One `CNAME` for `www`:

```
www  ->  rokasge.github.io
```

## Local preview

Open `index.html` directly in a browser. Note: `file://` won't auto-serve
`rasome/index.html` for the URL `rasome/` — open `rasome/index.html` explicitly.
GitHub Pages handles that automatically.

## Design

- Light theme: `#ffffff` bg / `#1c1e21` fg / `#1a5fd0` accent
- All colours are tokens in `:root`; nothing hardcoded outside it
- Body text, dim text, headings and accent all pass WCAG AA (4.5:1) on both the
  page background and the panel background
- Favicon: inline `data:` SVG — a square outline on a white plate
- Zero external requests; no trackers, cookies, or analytics

## Research (not published)

Background research that informs the copy lives outside this repo:

- `~/research/EU-Lithuania-Cybersecurity-Audit-Requirements-Report.md` —
  NIS2/KSĮ audit obligations, who may perform them, qualification routes
- `~/lt_recon/LITHUANIAN_SECURITY_VENDORS_REPORT.md` — verbatim Lithuanian
  market vocabulary and site structure from 5 commercial vendors + NKSC

Keep these out of the repo — they name competitors and contain unverified items.
