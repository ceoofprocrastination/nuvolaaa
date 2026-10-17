# Nuvola Diary

A static, local-first journaling PWA. Open `index.html` for the app or `landing.html` for the introduction. `app.html` is kept as a compatibility entry point for existing install/service-worker URLs.

## Run locally

Serve this directory over HTTP (service workers and module workers do not work reliably from `file://`):

```sh
python -m http.server 8080
```

Then open `http://localhost:8080/index.html`.

## Storage and privacy

Entries and mood check-ins are stored in IndexedDB via Dexie. Appearance and optional coach preferences are stored in localStorage. The optional on-device coach downloads model assets from its configured CDNs; journal content is not sent to a remote application backend. Export a JSON backup from **You → Your data** before clearing browser data.

## Deployment

Deploy the directory as a static site on Vercel. The service worker shell cache includes `app.html`, `index.html`, `landing.html`, the manifest and icon.
