# UApply — static PWA package

A shareable, installable static build of the **UApply** Canadian university
application tracker (dashboard, application tracker, score tracker, Kira
interview prep, ApplyBot simulation).

## What's in here

- `index.html` — the whole app (self-contained single page)
- `manifest.webmanifest` — PWA manifest (installable, standalone display)
- `sw.js` — service worker: offline-first caching of the app shell
- `icons/` — app icons (192/512 PNG, maskable, Apple touch icon, favicons)

## Check into git / deploy

```bash
git init
git add .
git commit -m "Add UApply static PWA"
```

Deploy the folder as-is to any static host (GitHub Pages, Netlify, Vercel,
Cloudflare Pages, nginx, …). Serve over **HTTPS** — service workers and
"Add to Home Screen" require it.

## Notes

- Each visitor's data (applications, scores, practice) is stored in their own
  browser (`localStorage`); nothing is sent to a server.
- The service worker precaches the app shell on first visit, so the app keeps
  working offline after that.
- To refresh the package after the app changes, re-export and rebuild.
