# KHERJA

Ride-hailing application (passenger, driver, admin). Node.js 22.23.4, SQLite (`node:sqlite`), vanilla HTML/CSS/JS, zero npm dependencies. Arabic (RTL) and French (LTR).

- Passenger and driver apps: `/app` and `/app/driver` (one shell, `app/kherja.html`). Admin: `/admin`.
- In non-dev mode `/`, `/index.html` redirect to `/app` and `/driver` to `/app/driver` (302, `no-store`). In dev mode the old pages stay reachable for the legacy test suites.
- Fonts: Tajawal (Arabic) and Plus Jakarta Sans (Latin), self-hosted in `app/fonts` (SIL OFL licenses included).

## Run locally (dev only)
```
KHERJA_DEV=1 node backend/server.js        # loopback only, OTP code is 123456, never use with real data
node app/build-shell.js && node app/build-apps.js   # rebuild app/kherja.html, admin.html, driver.html after editing sources
```
## Tests
`npm run test:backend`, `npm run test:ops`, `npm run test:e2e` (needs Playwright + Chromium). Current numbers: see `TEST-REPORT.md`.

## Documents
`DEPLOYMENT-STAGING.md`, `SECURITY-REVIEW.md`, `TEST-REPORT.md`, `OPERATIONS.md` (runtime, backup/restore, rollback), `docs/RELEASE-GATE.md` (status per requirement).

## Provenance
The Git history in this repository starts from a *reconstructed* baseline (`2.3.0-reconstructed-ab`); the original project history was not recovered and is not claimed. All later commits are real, individual changes.

## Not integrated (honest status)
SMS/OTP provider, push notifications, payments, real maps/geocoding and live GPS are **not** implemented. The app never simulates them.
