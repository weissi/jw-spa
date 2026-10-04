# jw-spa

A collection of tiny single-page apps. Each app lives in its own subdirectory
and is a **single self-contained HTML file** — inline CSS and JavaScript, no
frameworks, no build step, no external requests (no CDNs, no webfonts).
Everything works straight from the file itself.

Live at `https://weissi.github.io/jw-spa/` (GitHub Pages, `main` branch).

## Apps

| App | What it does |
|-----|--------------|
| [Coffee Division](coffee-division/) | Split a bag of coffee beans into even doses (18–22 g) with minimal leftover. |

## Conventions

- **One folder per app**, e.g. `coffee-division/`, containing a self-contained `index.html`.
- **Icons are inlined as data URIs.** The repo tooling cannot store binary
  files, so each app's icon is embedded directly in its HTML
  (`apple-touch-icon`) and in its `manifest.webmanifest`. This also keeps
  every app to plain text files.
- **iPhone home screen:** each app ships iOS meta tags
  (`apple-mobile-web-app-capable`, `apple-mobile-web-app-title`) plus a
  `manifest.webmanifest`, so Safari → Share → Add to Home Screen just works.
- **Version footer:** every app shows `vX.Y · build YYYY-MM-DD HH:MM TZ` in
  its footer, bumped on every change (build time included, since apps change
  often).
- **Root `index.html`** links every app with its icon and current version.

## Adding a new app

1. Create `<name>/index.html` — fully self-contained, no external requests.
2. Generate an icon, inline it as a data URI for `apple-touch-icon`.
3. Add `<name>/manifest.webmanifest` (icons as data URIs).
4. Add a card to the root `index.html` and a row to the table above.
5. Push to `main` — GitHub Pages redeploys automatically.

## Deploy

GitHub Pages serves the `main` branch. Apps are reachable at
`https://weissi.github.io/jw-spa/<name>/`.
