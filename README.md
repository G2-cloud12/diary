# DAYSPACE

A single-page, anime-inspired personal diary and life organizer. This project is designed for static hosting on **GitHub Pages**.

## Included files

- `index.html` — the DAYSPACE application and its existing diary features.
- `manifest.json` — installable web app metadata.
- `sw.js` — service worker for caching the app shell for offline reopening.
- `icon.svg` — application icon.
- `.nojekyll` — tells GitHub Pages not to run Jekyll processing.

## Deploy to GitHub Pages

1. Create a GitHub repository (for example, `dayspace`).
2. Upload all files in this folder to the repository's **root**. Keep the filenames unchanged.
3. In GitHub, open **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Select the `main` branch and `/ (root)`, then save.
6. Wait for GitHub Pages to publish the site. Open the URL shown in the Pages settings.

The app uses relative paths, so it can run from a GitHub Pages project URL such as `https://username.github.io/dayspace/`.

## Data storage and backups

- Diary entries, thoughts, notes, reminders and settings are stored in **IndexedDB in this browser on this device**.
- No account or cloud service is configured. Data is not automatically synchronized between devices or browsers.
- Open **Settings → Export JSON** regularly and keep the downloaded backup somewhere safe (for example, an external drive or your own cloud-drive folder).
- To restore, open **Settings → Import JSON** and choose a DAYSPACE backup. Import merges entries with existing data; it does not intentionally erase current entries.
- Clearing browser/site data can erase the local database. Export a backup first.

## Offline use and reminders

The service worker caches the app shell so the site can reopen offline after its first successful load on HTTPS. Google Fonts and other external resources may still require an internet connection.

Reminder checks and browser notifications work while DAYSPACE is open in a supported browser. A static GitHub Pages site cannot guarantee scheduled notifications when the browser is fully closed.

## Local testing

For service-worker and installability testing, serve the folder over HTTP rather than opening `index.html` as a `file://` URL. For example, with Python installed:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000/`.

## Privacy

The application is local-first. Do not share exported backup JSON files: they may contain private diary entries, notes and reminders.
