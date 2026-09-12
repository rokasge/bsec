# Client-audit variant brief — SHARED SPEC

Read this fully before writing. All 5 variants exist so the user can compare
**structures**, not copy. The content below is FIXED. Do not invent services,
prices, certifications, client names, or claims. Do not add testimonials.

## Business context

baltsec.com — independent security research / penetration testing, based in the
Baltics. Target audience: **companies who would BUY a security audit** (CISO,
CTO, engineering lead, compliance owner). Not recruiters, not fellow researchers.

The existing site is a researcher's personal page. These variants must speak to
a **buyer of audit services**, not a peer. Lead with commercial value, not
exploit technique.

## Fixed facts — use exactly these

- Name: baltsec
- Tagline: `security research`
- Location: based in the Baltics
- Contact: `contact@baltsec.com` (ONLY this — no abuse@, no GitHub, no phone)
- Email call-to-action: "Request an audit" / "contact@baltsec.com"

## Service lines — use all five, wording may be tightened but not changed in meaning

1. **Web Application & API Penetration Testing**
   Manual testing to find exploitable flaws before attackers do. Auth, access
   control, injection, business-logic abuse, API authorization.
2. **Vulnerability Research (Auth Bypass, Injection, Deserialization)**
   Deep-dive research into authentication, injection, and unsafe deserialization
   in custom and enterprise software.
3. **Enterprise Software & CMS Security Reviews**
   Security review of enterprise platforms and CMS deployments, from
   configuration through to source-level issues.
4. **Android Application Assessments**
   Mobile application assessment covering storage, transport, authentication,
   and inter-process communication.
5. **CVE Coordination & Advisory**
   Coordinating disclosure with vendors and assigning CVEs where warranted.

## Process — the audit engagement (use this, it is the core of the offer)

1. **Scoping** — agree targets, rules of engagement, and out-of-scope systems
   in writing before any testing begins.
2. **Testing** — manual assessment against the agreed scope, reported as it
   progresses so findings are never a surprise at the end.
3. **Reporting** — a written report: each finding with severity, reproduction
   steps, business impact, and a concrete remediation.
4. **Retest** — after remediation, findings are re-tested and the report is
   updated. Free of charge and without a time limit.

## Disclosures / working terms — use these exact claims

- Encrypted communications accepted (PGP on request)
- Zero exploit code published prior to a fix
- Zero client names published without written permission
- Medium-severity issues: courtesy credit / hall of fame
- Critical-severity: full write-up + CVE coordination

## Deliverable per variant

- `variants/<id>/index.html` — self-contained. Must work opened directly from
  disk via `file://`.
- `variants/<id>/style.css` — variant's own stylesheet.

**Paths MUST be relative** (`style.css`, not `/style.css`) — root-absolute paths
break local `file://` preview. This is a hard requirement.

## Hard constraints (all variants)

- **No javascript at all** — no `<script>`, no inline `on*=` handlers.
- **No external requests** — no CDN, no Google Fonts, no remote images.
  System font stack only. Favicon must be an inline `data:` URI if used.
- Static HTML + CSS only. No build step.
- Dark theme. Palette around: bg `#0a0a0a`, fg `#d4d4d4`, dim `#6a6a6a`,
  faint `#2a2a2a`. You may add ONE accent colour. Do not go bright/light theme.
- Monospace-leaning typography is on-brand but you may pair it with a
  system sans for body text if your layout benefits.
- Must be responsive down to 360px wide. Test mentally: no horizontal overflow.
- Accessible: real heading hierarchy (one `<h1>`), `:focus` visible, body text
  contrast >= 4.5:1, `prefers-reduced-motion` respected if you animate.
- Semantic HTML. No `<div>` soup where a `<section>`/`<article>`/`<ul>` belongs.
- Footer must include: `no trackers, no cookies, no javascript`.

## HTML skeleton all variants must follow

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TITLE</title>
<meta name="description" content="DESC">
<link rel="icon" href="data:image/svg+xml,...">
<link rel="stylesheet" href="style.css">
</head>
<body>
  <!-- content -->
</body>
</html>
```

## ASCII logo (optional — use if your design wants it)

Variants that want the ASCII wordmark should use this exact glyph set
(figlet `standard`, already correct — do not retype it by hand, copy it):

```
 ____        _ _                 
| __ )  __ _| | |_ ___  ___  ___ 
|  _ \ / _` | | __/ __|/ _ \/ __|
| |_) | (_| | | |_\__ \  __/ (__ 
|____/ \__,_|_|\__|___/\___|\___|
```

Wrap it in `<pre>` with `white-space:pre` and scale with `clamp()` so it never
wraps. Do NOT hand-type variations of these glyphs — misalignment is the single
most common failure. If your design doesn't want ASCII art, skip it entirely.

## Deliverable report (return in your final summary)

Return EXACTLY:
1. The design thesis in 2 sentences — what layout idea drives this variant.
2. Absolute paths of the two files you wrote.
3. The accent colour hex, if you used one.
4. What a buyer sees in the first 3 seconds (above-the-fold summary).
5. Any spec item you could not implement, and why.
