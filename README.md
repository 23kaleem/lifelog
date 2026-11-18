# Life Log

A personal daily tracker that runs as an iPhone home-screen app. It tracks water, prayers, Quran pages, runs, gym, football, creatine, night skincare and any trackers you add yourself.

- All data is stored **on your phone only**. Nothing is sent to this website or anywhere else.
- Works offline once installed.
- No cost and no accounts beyond this free GitHub page.

**Version 1.2.0**
- A redesigned look in the style of Apple Fitness, with Liquid Glass controls.
- A new Summary with comparisons against the last period, a prayer-by-weekday heatmap, when you drink, run pace and personal bests, streak records, a year overview and the gym split.

## Install on iPhone
1. Open this site's link in **Safari**.
2. Tap **Share** → **Add to Home Screen** → **Add**. If you see **Open as Web App**, keep it switched on.
3. Always open Life Log from the home-screen icon. Data logged in a Safari tab isn't shared with the home-screen app.

## Back up your data
In the app, go to **Settings → Back up to Files / iCloud** about once a week and save the file to iCloud Drive. To move to a new phone, install the app there and use **Restore from backup**.

⚠️ Deleting the home-screen icon deletes the app's data. Back up first.

## Updating the app
1. Upload the new files to this repository, replacing the old ones.
2. In `sw.js`, raise the number in `CACHE = 'lifelog-v3'` (for example to `lifelog-v4`). In `index.html`, raise `VERSION`.
3. On the phone, close and reopen the app once or twice. Your data isn't affected.

## Files
| File | What it is |
|---|---|
| `index.html` | The whole app |
| `sw.js` | Lets it work offline |
| `manifest.webmanifest` | App name and icon for the home screen |
| `icon-*.png` | App icons |
| `PRODUCT.md`, `DESIGN.md`, `CLAUDE.md` | Notes on the product and design, for future changes |
