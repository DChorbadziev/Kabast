# Кабаст Отпад 2026 — Општина Аеродром

## Project Overview
A single-file static HTML page listing all bulky waste (кабаст отпад) collection locations and dates for Aerodrom municipality, Skopje, for the 2026 spring campaign (18 May – 9 July 2026).

The goal is to deploy this as a public GitHub Pages site.

## File
- `index.html` — the entire app, self-contained (HTML + CSS + JS + Leaflet map)

## What the app does
- **Map tab**: Leaflet.js map with OpenStreetMap/CARTO dark tiles. All 41 drop-off locations are pinned with color-coded markers (yellow = upcoming, orange = active, grey = done). Clicking a pin shows a popup with the neighborhood, address, dates, **Google Maps link**, and a **share button**. Legend overlay on the map explains dot colors.
- **Schedule tab**: Full chronological list grouped by month (May / June / July). Clicking a row switches to the map and opens that location's popup.
- **Live status**: Each entry is automatically classified as `upcoming`, `active`, or `done` based on `new Date()` vs the entry's date range.
- **Search + filter**: Works across both tabs simultaneously — filters map markers and schedule rows together.
- **Next-upcoming banner**: Yellow banner below the header auto-updates to show the next upcoming location (or active location during the campaign). Clickable.
- **Admin mode**: Click the title 5 times (or add `#admin` to URL) to enter admin mode. Enables inline editing, add/delete entries, save to localStorage, and JSON export/import for backup.

## Tech stack
- Pure HTML/CSS/JS — no build step, no framework
- Leaflet.js 1.9.4 via CDN (`cdnjs.cloudflare.com`)
- CARTO dark tile layer (requires internet to load map tiles)
- Google Fonts: Bebas Neue + IBM Plex Mono + IBM Plex Sans (via CDN)

## Deployment
**Live:** `https://dchorbadziev.github.io/Kabast/`
**Repo:** `https://github.com/DChorbadziev/Kabast`

## Complete features
- [x] Push `index.html` to GitHub and enable Pages
- [x] Add a legend to the map explaining the dot colors
- [x] Add a "next upcoming location" banner at the top
- [x] Make the map fit full viewport height better on mobile
- [x] Tile provider kept as CARTO (dark_all) — reliable and fast
- [x] Add share/copy link button per location
- [x] Add "Open in Google Maps" link in popups
- [x] Add admin mode (5× click title or `#admin` URL hash): inline edit, add/delete, localStorage persistence, JSON export/import
