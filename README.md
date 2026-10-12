# Platinum Ops — v0.0.1

A private, mobile-first PWA starter for pool-business operations, inspired by Platinum Pools NSW's premium, locally focused branding. This is an internal tool, not a customer-facing website.

## Included in v0.0.1
- Dashboard overview
- Job register with client/site details, status, notes and plan/document references
- Quote builder with editable line items, quantity × unit rate, GST, totals, and print/save as PDF
- Earthworks calculator: rectangular/circular volume, swell allowance, loose volume, truckloads and disposal allowance
- Quick links to NSW pool safety, planning, legislation, SafeWork, Before You Dig, BOM and selected local councils
- JSON export/import backup
- PWA manifest, offline app shell and update-on-reopen service worker
- Visible version label

## Deploy to GitHub Pages
1. Create a GitHub repository for the app.
2. Upload `index.html`, `manifest.webmanifest`, and `sw.js` to the repository root.
3. In repository Settings → Pages, deploy from the `main` branch and `/ (root)`.
4. Open the resulting HTTPS URL on the phone, then use Safari Share → Add to Home Screen (iPhone) or the browser install option (Android).

## Updating the app
For each release:
1. Edit the app files and commit/push to GitHub.
2. Change `VERSION` in `index.html` and the visible `v0.0.1` labels.
3. Change `CACHE_VERSION` in `sw.js` to a new unique value, e.g. `platinum-ops-v0.0.2`.
4. Keep `updateViaCache: 'none'`, the startup `reg.update()` call, and `skipWaiting()` / `clients.claim()` behaviour.

When the installed app is reopened online, it checks the service worker for a new version. The new worker activates and the page reloads. Offline, the last cached app shell remains available. A network connection is needed to receive new releases.

## Important limitations
- v0.0.1 saves jobs and quotes to local browser storage on the current device only. It does not sync between phone and computer and has no login, team access controls or server backup.
- Job plan files are not uploaded; save a filename or link/reference for now.
- Export JSON backups regularly. Clearing browser data can remove local records.
- Calculations are rough estimating aids. Confirm excavation geometry, swell, truck payload/capacity, disposal fees and compliance requirements for each job.
- Check government and council websites for current, project-specific rules. Links are provided as starting points, not legal advice.

## Privacy
Do not put sensitive client data or confidential plans in this prototype until authentication, access control and secure cloud storage are implemented.
