# My Investment Portfolio — Privacy-First PWA

## Privacy model

The published GitHub Pages files contain **no personal portfolio values or CAS data**.

When you import a CAS PDF:
- The PDF is read in the browser.
- Portfolio snapshots are stored in IndexedDB on the device.
- No app endpoint receives the CAS, PAN, folio numbers or portfolio history.
- `Delete local portfolio data` clears the app's local database.

### PDF parser dependency

The app uses PDF.js from cdnjs to parse PDFs in the browser. This downloads the parser code, **not your CAS data**. The CAS itself is passed directly to PDF.js in the browser.

## Current Version 2 capabilities

- Blue/navy mobile-first dashboard
- PWA manifest and service worker
- Local IndexedDB portfolio storage
- Local CAS PDF import
- Local portfolio snapshot history
- Local portfolio value line chart
- Install-to-home-screen support
- No hard-coded personal portfolio values

## GitHub Pages

Upload these files to the repository root:

- `index.html`
- `manifest.json`
- `service-worker.js`
- `icons/icon-192.png`
- `icons/icon-512.png`

Then enable GitHub Pages from `main` / root.

## Important limitation

CAS parsing is intentionally conservative in this first privacy-safe build. It extracts the portfolio market-value snapshot and basic scheme count. The next version can add robust scheme-level extraction, XIRR, AMC allocation and transaction-level history without changing the privacy model.
