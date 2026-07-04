# The Learning Map of India

India's education data, charted one map at a time.

## Local development

Requires Node.js 18+.

```bash
npm install
npm run dev
```

Open http://localhost:4321 — you should see the homepage, with working
navigation to Atlas / About / Sources. The Atlas page is intentionally
empty right now; maps get added in a later step.

## Before deploying

Edit `astro.config.mjs`:

- Set `site` to `https://YOUR-GITHUB-USERNAME.github.io`
- Set `base` to `/YOUR-REPO-NAME` (delete the `base` line entirely if this
  repo is itself named `YOUR-GITHUB-USERNAME.github.io`)

## Deploying to GitHub Pages

1. Push this repo to GitHub.
2. In the repo settings, go to **Pages** and set the source to
   **GitHub Actions**.
3. Push to `main` — the workflow in `.github/workflows/deploy.yml` builds
   and deploys automatically. Your site will be live at the `site` + `base`
   URL you set above.

## Project structure

```
src/
  layouts/BaseLayout.astro   → shared page shell (head, header, footer)
  components/                → Header, Footer, LegendCard (reusable "map key" card)
  pages/                     → index.astro, about.astro, sources.astro, atlas.astro
  styles/global.css          → design tokens (colors, type, spacing)
data/
  raw/                       → future home for downloaded datasets
  processed/                 → future home for cleaned, map-ready JSON
scripts/                     → future home for Python data-cleaning scripts
```

## Design system quick reference

| Token | Value | Use |
|---|---|---|
| `--blackboard` | `#1e3b32` | Header, footer, hero background |
| `--paper` | `#ede6d3` | Page background |
| `--chalk` | `#f4f1e4` | Text on dark backgrounds |
| `--marigold` | `#e8a93b` | Primary accent, highlights |
| `--notebook-blue` | `#35577d` | Links, secondary accent |
| `--red-pen` | `#a23b2e` | Sparing emphasis accent |
| Display font | Kalam | Headlines only |
| Body font | Work Sans | All body copy |
| Mono font | IBM Plex Mono | Nav, buttons, data labels, citations |
