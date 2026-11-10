# Memory Match PWA

A plain HTML, CSS and JavaScript memory game configured as an installable Android PWA.

## Files
- `index.html` — game, styling and JavaScript
- `manifest.json` — install metadata and landscape preference
- `service-worker.js` — offline app-shell caching
- `icon-192.png`, `icon-512.png` — app icons

## Run locally
A service worker requires a secure context. For local testing, use `http://localhost` rather than opening the HTML file directly.

If Python is installed:
```bash
python -m http.server 8000
```
Then open `http://localhost:8000`.

## Publish with GitHub Pages
1. Create a GitHub repository (public is simplest for GitHub Pages on the free plan).
2. Upload all files from this folder to the repository root.
3. In repository Settings → Pages, choose deployment from the `main` branch and `/ (root)`.
4. Wait for the published HTTPS URL.
5. Open that URL in Chrome on the Android tablet.
6. Use the Install button if Chrome offers it, or Chrome menu → Install app / Add to Home screen.

## Offline use
Open the hosted app once while online and allow it to finish loading. The service worker caches the app shell. Then launch the installed app; the game itself does not need an internet connection.

## Updating later
After changing app files, change `CACHE_NAME` in `service-worker.js` (for example, `memory-match-pwa-v2`) so installed copies fetch the new version.
