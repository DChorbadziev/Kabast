# Кабаст Отпад 2026 — Општина Аеродром

## Project Overview
A single-file static HTML page listing all bulky waste (кабаст отпад) collection locations and dates for Aerodrom municipality, Skopje, for the 2026 spring campaign (18 May – 9 July 2026).

The goal is to deploy this as a public GitHub Pages site.

## File
- `index.html` — the entire app, self-contained (HTML + CSS + JS + Leaflet map)

## What the app does
- **Map tab**: Leaflet.js map with OpenStreetMap/CARTO dark tiles. All 38 drop-off locations are pinned with color-coded markers (yellow = upcoming, orange = active, grey = done). Clicking a pin shows a popup with the neighborhood, address, and dates.
- **Schedule tab**: Full chronological list grouped by month (May / June / July). Clicking a row switches to the map and opens that location's popup.
- **Live status**: Each entry is automatically classified as `upcoming`, `active`, or `done` based on `new Date()` vs the entry's date range.
- **Search + filter**: Works across both tabs simultaneously — filters map markers and schedule rows together.

## Tech stack
- Pure HTML/CSS/JS — no build step, no framework
- Leaflet.js 1.9.4 via CDN (`cdnjs.cloudflare.com`)
- CARTO dark tile layer (requires internet to load map tiles)
- Google Fonts: Bebas Neue + IBM Plex Mono + IBM Plex Sans (via CDN)

## Deployment target
**GitHub Pages** — rename `index.html`, push to `main` branch, enable Pages in repo settings.
URL will be: `https://<username>.github.io/<repo-name>`

## Possible improvements / tasks
- [ ] Push `index.html` to GitHub and enable Pages
- [ ] Add a legend to the map explaining the dot colors
- [ ] Add a "next upcoming location" banner at the top
- [ ] Make the map fit full viewport height better on mobile
- [ ] Consider switching tile provider if CARTO is slow (e.g. OpenStreetMap standard tiles)
- [ ] Add share/copy link button per location
