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

## Enabling GitHub Pages (one-time, in the browser)

The workflow is ready, but Pages has to be switched on for the repository once:

1. Open **Settings → Pages** in this repository.
2. Under **Build and deployment → Source**, choose **GitHub Actions**.
3. Re-run the **Deploy to GitHub Pages** workflow from the **Actions** tab
   (or push any commit) — the site publishes at the URL above.

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
