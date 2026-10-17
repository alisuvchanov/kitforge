# KitForge

A free, open-source, browser-based football shirt design studio: edit a shirt, review the design with transparent rules, save projects locally and export artwork.

This repository is a **single static file** (`index.html`). There is no framework, no build step, no package manifest, no backend and no environment variables.

## Run locally
Open `index.html` in a browser, or serve the folder: `python3 -m http.server 8000` then visit http://localhost:8000

## Features
- Three SVG shirt constructions, front and back views, six pattern families, three collars, three cuff styles.
- Colours, text, typeface, crest upload (PNG, JPEG, WebP, max 300 KB) and sponsor text.
- Undo and redo, project library (save, open, duplicate, delete, search, sort).
- Design review: weighted score from documented rules, with measured checks separated from advice.
- Export SVG, PNG and project JSON; import JSON.
- Six original example designs using fictional teams.

## Limitations
- Projects live in browser localStorage: no cross-device sync, not a backup, cleared if site data is cleared. Export JSON for copies.
- Exports are concept artwork, not manufacturing files. No colour profile, bleed or print specification is defined.
- The review score is a heuristic. It does not predict quality, sales or competition compliance.
- KitForge is free. There are no paid plans, accounts or payments, and none are planned.
- No automated browser tests are included. See the checklist in the audit report.
- Loads the Archivo font from Google Fonts; falls back to system fonts if blocked.

## Security boundaries
- No uploaded or imported content is executed. User text is HTML-escaped; colours, fonts and enums are whitelisted; crest images must be PNG, JPEG or WebP data URLs with a matching file signature and are shown only as images. SVG uploads are not accepted.
- Imports are limited to 1 MB and re-validated field by field. Stored data is re-validated on load.
- This is not a full security audit. All logic runs in the browser and can be modified by the user, so nothing here can be treated as a trusted entitlement or payment check.

## Deploy (Vercel)
Import the repository, set Framework Preset to "Other", leave Build Command and Output Directory empty. No environment variables are needed.

## Licence
The project is intended to be open source, but no licence has been selected yet. Add a `LICENSE` file (for example MIT or Apache-2.0, with your name as copyright holder) before publishing. Until then, default copyright applies and others have no permission to reuse the code.
