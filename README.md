# Europe · 欧洲之旅 · September 2026

A single-page, offline-friendly trip companion: bilingual (EN / 中文) day-by-day
itinerary with route overview, day navigation, booking status, and map links.

**Live site:** https://aforapple937.github.io/travel-/

## What's here

| File | Purpose |
| --- | --- |
| `index.html` | The whole app — HTML, CSS and JS in one file. No build step, no dependencies. |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is. |
| `.github/workflows/pages.yml` | Builds and publishes the site to GitHub Pages on every push. |

The only external requests are Google Fonts; everything else runs locally in the
browser, so the page still works fine without a network connection (with fallback fonts).

## Enabling GitHub Pages — one manual step

Everything is committed and the deploy workflow is in place, but **Pages itself has to
be switched on once from the browser.** A workflow cannot do this for you: the
`GITHUB_TOKEN` it runs with is not allowed to create a Pages site
(`Resource not accessible by integration`), so the first two runs fail until you do this:

1. Open **Settings → Pages** in this repository.
2. Under **Build and deployment → Source**, pick **GitHub Actions**.
3. Go to the **Actions** tab → **Deploy to GitHub Pages** → **Re-run all jobs**
   (or just push any commit).

The site then publishes at the URL above, and every later push redeploys it automatically.

If the repository is private, note that Pages on private repos requires a paid plan —
making the repository public is the free route.

## Editing the itinerary

All trip data lives in the `DAYS` array inside the `<script>` block at the bottom of
`index.html`. Each entry holds the date, city, hotel and the day's events, with `en`
and `zh` strings side by side. Edit, commit, push — the workflow redeploys automatically.

## Running it locally

Open `index.html` directly in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```
