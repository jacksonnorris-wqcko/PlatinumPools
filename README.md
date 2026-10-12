# Platinum Ops — v0.0.2

A private, mobile-first PWA starter for Platinum Pools NSW. This is an internal business tool, not a consumer-facing website.

## v0.0.2 branding update
- Uses the supplied Platinum Pools NSW logo in the app navigation and header.
- Uses the supplied logo artwork for the PWA icon and iPhone `apple-touch-icon`.
- Updates the visible version to v0.0.2 and bumps the service-worker cache.
- Preserves the existing local storage key so v0.0.1 job and quote data is not deliberately discarded by this release.

## Deploy to GitHub Pages
1. Unzip this folder and upload the **contents** of `platinum-pools-app-v0.0.1` to the repository root (or keep the folder and configure Pages to serve it).
2. In repository Settings → Pages, deploy from the `main` branch and `/ (root)`.
3. Open the resulting HTTPS URL in Safari on the iPhone, then use Share → Add to Home Screen.
4. If the app was already installed, open it online after deploying; the service worker checks for the new version. If the old icon remains, remove the home-screen shortcut and add it again so iOS refreshes the installed icon artwork.

## Updating the app
For each release, update the visible `VERSION` and labels in `index.html`, bump `CACHE_VERSION` in `sw.js`, and ensure any new assets are in `APP_SHELL`. The app checks for service-worker updates when reopened online, installs the new cache, and activates the new worker. Offline, the cached app shell remains available.

## Current limitations
- Jobs and quotes are stored in the current browser on the current device only; no account, cross-device sync, or server backup yet.
- Plans are references only; files are not uploaded in this version.
- Export JSON backups regularly. Clearing browser data can remove local records.
- Earthworks calculations are estimates; confirm geometry, swell, truck capacity, disposal rates and project requirements.
- Government/council links are starting points; verify current requirements for each property and approval pathway.

## Privacy
Do not store confidential client plans or sensitive personal data until authentication, access control and secure cloud storage are implemented.
