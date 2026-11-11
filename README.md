# TravelFx upgraded

A static HTML/CSS/JavaScript currency converter. No build step is required.

## Included

- `index.html` – the app
- `manifest.webmanifest` – installable web-app metadata
- `sw.js` – basic offline app-shell caching
- `icon-192.png` and `icon-512.png` – app icons

## Deploy to Cloudflare Pages

1. Create a GitHub repository (for example, `travelfx`).
2. Upload all files in this folder to the repository root.
3. In Cloudflare Pages, create a project and connect the repository.
4. Choose **None** as the framework preset. Leave the build command blank and set the output directory to `/` (the repository root).
5. Deploy. Cloudflare will provide a `*.pages.dev` URL.

The app uses no server-side build process. For PWA installation, serve it over HTTPS (Cloudflare Pages does this automatically).

## Saving and sharing

- Local presets are saved in the current browser's `localStorage` and are not automatically synced between devices.
- Share links encode a versioned snapshot in the URL hash. Anyone with the link can load that exact currency list and base currency.
- A snapshot link does not update when the original user later changes a preset. True persistent shared links need a database and an authenticated editing flow; Supabase can be added as a separate next step.

## Notes

- Rates are fetched from `https://open.er-api.com/v6/latest/USD` and cached locally for up to 12 hours. The manually triggered refresh bypasses the cache.
- The app includes indicative conversion rates and is not intended as a source of transaction quotes.
- Tailwind CSS, Lucide icons and QRCode.js are loaded from public CDNs. An internet connection is needed to load those libraries unless you vendor them locally.
