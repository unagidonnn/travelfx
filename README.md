# TravelFx – Mobile keypad update

This is the next static-site update for TravelFx. It keeps the existing currency conversion, saved presets, snapshot sharing, QR sharing, and exchange-rate cache, and improves expression entry on touchscreens.

## What's new

- A full 4-column calculator keypad with digits, decimal point, brackets, and `+`, `−`, `×`, `÷` operators.
- Larger touch targets (at least 46 px on typical phone screens).
- Cursor-aware insertion and deletion, so a key can be inserted in the middle of an expression instead of only at the end.
- Clear, Delete, and Done controls.
- On touch devices, the app uses its own keypad by default to avoid the Samsung decimal-only keyboard.
- Tap the small keyboard button beside an amount field, or **Use phone keyboard** in the keypad, to switch to the normal phone keyboard. Tap `123` to switch back.
- Service-worker cache version updated so deployed devices can receive the new app shell.

## Deploy the update to GitHub Pages

1. Download and extract this ZIP file.
2. Open your existing `travelfx` GitHub repository.
3. Upload the files from this folder to the repository root, replacing the existing files when prompted. In particular, replace `index.html` and `sw.js`.
4. Commit the changes. GitHub Pages will publish the update using your existing Pages configuration.
5. Open TravelFx on your phone and refresh. If you installed it as a PWA, close and reopen it after the site has updated.

The ZIP includes `index.html`, `sw.js`, `manifest.webmanifest`, and the existing app icons. It does not require a build step.

## Notes

- Local presets remain stored in the current browser's local storage.
- Share links remain URL snapshots and are not changed by this update.
- Exchange rates continue to be fetched from `https://open.er-api.com/v6/latest/USD` and cached locally.
