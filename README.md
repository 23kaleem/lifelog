# Life Log

A personal daily tracker that runs as an iPhone home-screen app. It tracks water, prayers, Quran pages, runs, gym, football, creatine, night skincare and any trackers you add yourself.

- All data is stored **on your phone only**. Nothing is sent to this website or anywhere else.
- Works offline once installed.
- No cost and no accounts beyond this free GitHub page.

**Version 1.3.1**
- A bold new look, dark and light: swipeable cards, tap-to-log habit and prayer circles, and a round + button for quick logging.
- A cleaner Summary (Week, Month, Year) with a daily-goals headline and trend arrows, plus a Records tab for perfect days, personal bests and streaks.
- A black app icon (1.2.1).

## Install on iPhone
1. Open this site's link in **Safari**.
2. Tap **Share** → **Add to Home Screen** → **Add**. If you see **Open as Web App**, keep it switched on.
3. Always open Life Log from the home-screen icon. Data logged in a Safari tab isn't shared with the home-screen app.

## Back up your data
In the app, go to **Settings → Back up to Files / iCloud** about once a week and save the file to iCloud Drive. To move to a new phone, install the app there and use **Restore from backup**.

⚠️ Deleting the home-screen icon deletes the app's data. Back up first.

## Updating the app
1. Upload the new files to this repository, replacing the old ones.
2. In `sw.js`, raise the number in `CACHE = 'lifelog-v6'` (for example to `lifelog-v7`). In `index.html`, raise `VERSION`.
3. On the phone, close and reopen the app once or twice. Your data isn't affected.

## Files
| File | What it is |
|---|---|
| `index.html` | The whole app |
| `sw.js` | Lets it work offline |
| `manifest.webmanifest` | App name and icon for the home screen |
| `icon-*.png` | App icons |
| `PRODUCT.md`, `DESIGN.md`, `CLAUDE.md` | Notes on the product and design, for future changes |
