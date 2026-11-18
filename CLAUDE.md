# Life Log — project context for Claude Code

## What this is
Life Log is Kaleem's personal daily-life tracker. It's an **offline-first iPhone home-screen web app (PWA)** hosted free on **GitHub Pages** from this repository. There's no backend, no accounts and no running costs; staying that way is a hard requirement. It's single-user (Kaleem, on iOS), with UK date formats and weeks starting on Monday.

**Current version: 1.2.0** (`VERSION` in index.html) · service worker cache `lifelog-v3` (in `sw.js`).

1.2.0 (2026-11-18) is a full redesign built from the 1.0.0 source. The 1.1.0 source wasn't to hand, so 1.1.0's changes were redone and then went further. It replaces the live 1.1.0 look. The data model is unchanged.

## Files (repo root = what GitHub Pages serves)
| File | Purpose |
|---|---|
| `index.html` | The whole app: one `<style>` block, then one `<script>` block. Vanilla JS, no frameworks, no CDN, no build step. |
| `sw.js` | Service worker. Page requests are network-first (falling back to cache offline); other files are cache-first. |
| `manifest.webmanifest` | PWA name and icons. |
| `icon-180.png` (apple-touch-icon), `icon-192.png`, `icon-512.png` | App icons (current: white concentric rings on a blue gradient). The Settings app card also shows `icon-180.png`. |
| `README.md` | User-facing install, backup and update notes. |
| `PRODUCT.md` | Product truth: who it's for, the four ways it's used, the firm-accountability voice, constraints. |
| `DESIGN.md` (+ `.impeccable/design.json`) | The design system: tokens, type, components, rules. Read it before any UI change. |
| `.impeccable/` | Impeccable design tooling: surface brief and direction contract, decision mocks, review captures, and the `review/seed.html` + `review/frame.html` screenshot harness. Not needed by the app; it doesn't have to be uploaded. |
| `dev/test.js`, `dev/seed.js` | Referenced in older notes but **missing from this copy**. If they're in the GitHub repo, they still target the 1.1.0 markup. |

## Hard rules
1. **Never break existing data.** All data lives in the phone's `localStorage` under the key `lifelog.v1`. Any new field must be optional; `normalise()` merges stored data over `defaults()`. Never rename or remove fields without a migration. Test with an old backup.
2. **Every release:** bump `CACHE` in `sw.js` (`lifelog-v4`, `-v5`, …) and `VERSION` in index.html.
3. **No external requests or dependencies.** It must work fully offline. Charts are hand-drawn SVG and icons are drawn SVG (the `I` set).
4. **Keep the web address and icon stable.** On iOS, data belongs to the home-screen install at this URL. Renaming the repo or username, or changing the icon (which forces a reinstall), loses data unless Kaleem backs up and restores. Warn him before any change like that.
5. **iOS Safari is the target.** Use `env(safe-area-inset-*)` and 16px+ input font (to stop zoom on focus). Don't rely on haptics or push notifications (not available to web apps).

## Deploy flow (how Kaleem ships)
Edit → test locally → commit and push to `main` (or upload the files on github.com). Pages updates in 1–10 minutes. On the iPhone, fully close the app and reopen it to pick up the new version. Data is untouched by updates.

## Testing
Node isn't installed on Kaleem's PC, so checks run with Python and Chrome:
```bash
python -m http.server 8123     # from the repo root
```
- **By hand:** open `http://localhost:8123/.impeccable/review/seed.html` once to load 40 days of sample data (it overwrites this browser's local data), then open `http://localhost:8123/`. Use a 390×844 viewport.
- **Screenshots:** run headless Chrome against `seed.html?theme=light|dark&h=<height>&tab=today|summary|settings&per=week|month|year`. It seeds the data, then loads the app in a 390px frame. Use `--blink-settings=preferredColorScheme=1` for light and `0` for dark. Crop to 780px wide at scale factor 2.
- Look at light and dark screenshots after any UI change. Check the browser console for errors.

## Data model (`localStorage['lifelog.v1']`)
```js
{
  v:1, start:'YYYY-MM-DD',                 // first tracked day (lowered automatically on restore)
  settings:{
    waterGoal:2500, quick:[250,500,750],   // ml
    prayerGoal:5, lateCounts:false,        // whether "late" counts towards the goal
    runGoal:3, kmGoal:25, gymGoal:3, footGoal:1,
    lastBackup:ISOString|null, installDismissed:bool,
    trackers:[                             // simple trackers; built-ins can be hidden, not deleted
      {id:'quran',name:'Quran',emoji:'📖',type:'count',unit:'pages',step:1,goal:2,period:'day',builtin:true,show:true},
      {id:'creatine',...type:'check',goal:7,period:'week'},   // check: goal = days/week, 7 = daily
      {id:'skincare',name:'Night skincare',...type:'check',goal:7},
      // custom ones: id 'c_<uid>', type 'check'|'count'|'amount', unit, step, goal, period 'day'|'week'
    ]
  },
  days:{ 'YYYY-MM-DD': { w:[[timestampMs, ml],...], p:{fajr|dhuhr|asr|maghrib|isha:'on'|'late'|'missed'}, v:{trackerId:number} } },
  acts:[ {id, type:'run'|'gym'|'football', d:'YYYY-MM-DD', km, sec, split:'Upper'|'Lower'|'Full'|'Other', min, note, t} ]
}
```
Backup file: `{app:'lifelog', version, exported, data:<the object above>}`. It's saved through the iOS share sheet (`navigator.share` with files), falling back to a download.

## Code map (index.html `<script>`)
Sections are marked with `/* ---------------- NAME ---------------- */`:
- **dates / formatting**: `keyOf`, `parseKey`, `addDays`, `weekStart` (Monday), `range`, `num`, `L` (ml→L), `dur`, `pace`, `esc` (always escape user text).
- **state**: `defaults()`, `normalise()`, `save()`, `day(k)` (read-only), `dayW(k)` (writable).
- **metrics**: `waterTotal/Hit`, `prayerCounts/Hit`, `tVal`, `isDaily`, `tDayHit`, `weekProgress`, `runWeekHit`/`gymWeekHit`/`footWeekHit`, `tWeekValue/Hit`, `dailyGoals` (each goal carries a colour `c` and progress `p`), `streakDays`, `streakWeeks`.
- **UI**: global `UI = {tab, date, per, anchor}`. `render()` replaces `#app.innerHTML`, then moves the tab bubble (`placeBubble`) and syncs the scroll top bar (`syncTopbar`). Elements with `data-k` keep their previous class and style across a re-render on the same view, so CSS transitions play (bars, ring arcs, switches, prayer segments).
- **icons**: `I` (drawn SVG set), `ic(icon, colour, size)` icon tiles (`sm`, `xs`, `lg`, `solid`). Built-in trackers map to icons via `T_ICON`/`T_COL`. Custom trackers show their emoji inside the tile.
- **TODAY** `renderToday()`: title + date, glass ‹ › buttons, daily-goals hero (`goalRing`: one arc per goal, filled by progress), Water (big rounded litres, pill quick-adds), Prayers (segmented On time / Late / Missed), Habits, This week (Runs, Gym and weekly habits; football is logged via "Log another activity"), Logged today, Streaks (current + best/Record).
- **SUMMARY** `renderSummary()`: Week/Month/Year with ‹ ›.
  - Tiles with a comparison badge against the previous period (`prevRange`, `delta`).
  - Week: habit grid, prayers by day, which prayer slips, water per day, When you drink (`drinkCard`), run distance, Run pace (`paceCard`), Gym split (`gymSplitCard`).
  - Month: calendar, Prayers by weekday (`prayerWeekdayCard`), prayers by day, water per day, When you drink, Run pace, run distance by week, Gym split, weekly goals table.
  - Year: year at a glance (`yearCard`), Prayers by weekday, prayers by month, water by month, When you drink, run distance by month, Run pace, Gym split, month-by-month table.
  - All views end with Streaks vs your best (`streakBestCard`, using `bestDays`/`bestWeeks`).
  - Football shows only when logged in that period.
- **charts**: `barChart`, `stackChart`, `prayerByName`, `habitGrid`, `calendarCard`, `weekTable`, `monthTable`. Any element with `data-tip` shows a tooltip on tap.
- **SETTINGS** `renderSettings()`: iOS Settings-style app card (real icon, version, last backup), grouped rows with solid icon tiles and chevrons. Goal sheets, the tracker editor, backup/restore/CSV, erase.
- **sheets**: `openSheet(html, ctx)` / `closeSheet()`. `actSheet` (run/gym/football), `goalSheet`, `trackerSheet`.
- **actions**: one delegated click handler. `data-act="name"` maps to `A[name](el)`, and `data-tab` switches tabs.

## Design system
**DESIGN.md is the source of truth.** In short:
- **Look:** the iOS category standard made premium. The craft bar is Apple Fitness / Health and Apple's iOS 26 apps (chosen by Kaleem on 2026-11-17 over several bolder directions).
- **Surfaces:** a grouped background (#f2f2f7 light, pure black dark) with solid cards (#fff / #1c1c1e), a 22px radius, hairline border and soft offset shadow. No glow.
- **Type:** SF Pro text. Numbers use SF Pro Rounded (`--round`) with tabular figures.
- **Colours:** one hue per subject: water/accent, prayer, quran, creatine, skincare, habit, run, gym, foot.
- **White text only on the `-fill` tokens** (`accent-fill`, `on-fill`/`on-text`, `miss-fill`, `run-fill`, `gym-fill`, `foot-fill`). Coloured text uses the `-ink` tokens. These all pass 4.5:1. `--grey` is for utility icon tiles.
- **Status:** always colour plus a text label.
- **Liquid Glass only on floating controls:** the capsule tab bar with a sliding bubble (the only spring easing), the ‹ › header buttons, and the top bar that appears on scroll. Content cards stay solid.
- **Voice:** firm accountability. Misses are shown plainly ("Still open: …", red callouts such as "Fajr slips most on Saturdays").

## Decisions & history
- **Hosting:** GitHub Pages was chosen over a Claude-hosted artifact (no subscription dependency) and a Raspberry Pi (more upkeep; may be a future option for sync).
- **Rejected for now:** prayer times and the Hijri date, supplements beyond creatine, reminders/notifications and Apple Health (not possible without a server or native app).
- **Football:** off This week, Streaks and the Settings goals at Kaleem's request. It's still loggable via **Log another activity** and appears in Summary when present.
- **1.2.0 redesign (2026-11-17/18):**
  - Kaleem compared bolder looks (prayer beads, departure board, transit map, timetable, form guide) and kept the iOS standard, polished.
  - It passed two independent design-review rounds.
  - Summary gained 7 cards from an approved mockup: period comparisons, prayer × weekday heatmap, when you drink, run pace + bests, streaks vs best, year at a glance, gym split.
- **Icon:** three cleaner options were proposed (A: single blue ring on white; B: white ring and tick on blue; C: blue and green rings on white). **Not chosen yet.** Changing it needs a backup → re-add to Home Screen → restore.
- **Possible future idea:** a Raspberry Pi or other self-hosted sync, designed so the current app keeps working offline.

## Working with Kaleem
- He uses an iPhone and a Windows PC.
- He likes to see a plan and a mockup/screenshot before big builds. He sometimes asks for "a plan, don't build yet".
- He prefers short, clear explanations and plain language over jargon.
- After changes, show screenshots and give him exact upload/commit steps.
