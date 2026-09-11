# baltsec

Static site for **baltsec.com** — served via GitHub Pages.

## Deploy

Single-file static site. No build step.

1. Push `index.html` to `main`
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

Just open `index.html` in a browser. No server required.

## Notes

- Zero JavaScript dependencies — only a 1-line inline script for the footer year
- No trackers, cookies, or external requests
- Theme colours: `#0a0a0a` bg / `#d4d4d4` fg / `#6a6a6a` dim
- ASCII logo is figlet `standard` font, hand-inlined (no runtime dependency)
