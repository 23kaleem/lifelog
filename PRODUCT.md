# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

(An offline-first PWA installed to the iPhone home screen from Safari. iOS Safari is the only target.)

## Users

One person: Kaleem, on his own iPhone. Life Log is single-user forever; it will never be shared with or used by family or friends, so there are no accounts, roles, onboarding for strangers or multi-user states to design for.

He uses it in four situations, all of them real and frequent:

- **Quick taps all day.** Logging water, prayers and habits in a few seconds as they happen, then closing the app.
- **Evening check-in.** Catching up on the day once, filling in anything missed and seeing what's still left.
- **Weekly and monthly review.** Reading Summary to spot patterns, like which prayer slips most or how water trends.
- **Straight after training.** Logging a run (distance and time), a gym session (split and minutes) or football.

## Product Purpose

A personal daily-life tracker for water, the five daily prayers, Quran pages, runs, gym, football, creatine, night skincare and any custom trackers he adds. It exists to give an honest, at-a-glance record of whether he's keeping his daily and weekly commitments, and to keep that record over months and years.

Success means logging takes seconds, the day's state is obvious from one screen, and Summary makes slipping patterns impossible to miss.

## Positioning

It's built for exactly one life. The trackers, goals and terms are his own: prayers recorded as on time, late or missed; Quran by pages; runs by distance and pace; gym by split; weeks starting on Monday; UK dates. It runs entirely on his phone with no backend, no account and no cost. A general habit app can't truthfully claim either the fit or the zero dependency.

## Operating Context

- He opens it from the home-screen icon on an iPhone, often one-handed and in short bursts during the day.
- He keeps data safe with a manual backup through the iOS share sheet (to Files/iCloud), roughly weekly. Restoring from a backup is the only way to move to a new phone or survive a reinstall.
- He ships updates by editing on a Windows PC, testing locally, then pushing to `main` on GitHub Pages. The phone picks up a new version when the app is closed and reopened.

## Capabilities and Constraints

**What it does**
- **Today:** a daily goals ring, best streak, water (quick-add buttons plus undo), prayers (on time / late / missed), daily habits, This week (runs, gym, weekly habits), what's been logged today, and a streaks grid.
- **Summary:** week, month and year views. Tiles, water bars against a goal line, prayers stacked by day, "which prayer slips most", a habit grid, a month calendar, a weekly-goals table and a year table.
- **Settings:** goals, a tracker editor (count, check or amount trackers, per day or per week; built-in trackers can be hidden but not deleted), backup, restore, CSV export and erase.

**Hard constraints** (see CLAUDE.md for detail)
- Offline-first. No external requests, CDNs, frameworks or build step: one `index.html` plus a service worker.
- Free to run. Hosted on GitHub Pages, with no backend and no running costs.
- Data lives only in `localStorage['lifelog.v1']`. Existing data must never break: new fields are optional and anything renamed needs a migration.
- The web address and the icon must stay stable, because on iOS the data belongs to that home-screen install.
- Web-app limits on iOS: no push notifications, no haptics and no Apple Health.

**Undecided or open**
- The live site runs 1.1.0, but this repo was rebuilt from the 1.0.0 copy (see CLAUDE.md).
- A new icon hasn't been chosen (options A, B and C were proposed).
- Self-hosted sync, for example on a Raspberry Pi, has been floated as an idea but isn't a commitment.
- Prayer times, the Hijri date, reminders and Apple Health were rejected for now.

## Brand Commitments

- The name is **Life Log**.
- **Voice: firm accountability.** Misses should be clearly visible and losing a streak should sting a little. State facts plainly and don't soften or cheerlead them. A miss is a miss.
- **Copy rules:** plain, short English with no jargon. UK date formats.
- **Visual standard (confirmed 2026-11-17, after seeing alternatives):** the category standard for an iOS tracker, made premium and polished. Kaleem compared new directions (prayer-bead, departure-board, transit-map, timetable and form-guide looks) and chose the familiar iOS look. **The craft bar is Apple Fitness / Health and Apple's iOS 26 apps (e.g. Weather).** Liquid Glass comes back on floating controls only: the capsule tab bar with a sliding bubble, the glass ‹ › header buttons and the top bar that appears on scroll. Content cards stay solid.

## Evidence on Hand

- The live app and his real data are on his phone; neither is in this repo.
- The 1.0.0 source is in this folder.
- Mockups of the 1.1.0 restyle exist: `Downloads/life-log-mockup.png` and `Downloads/life-log-ios-mockup.png`, plus the screenshots shared on 2026-11-17.
- The `dev/seed.js` 40-day sample-data seeder and the `dev/test.js` Playwright test are referenced in CLAUDE.md but are missing from this copy.
- There are no testimonials, other users or metrics, and none should be invented.

## Product Principles

1. **Seconds to log.** The most common actions, like adding water or marking a prayer, take one tap from opening the app.
2. **Honest record.** Show misses as plainly as hits. Never hide, round up or reframe a slip.
3. **One glance, one day.** Today answers "what's done and what's left" without scrolling for the essentials.
4. **His data, his phone.** No dependency, account or cost that could ever cost him his history.
5. **Patterns over points.** Summary exists to surface what keeps slipping, not to decorate totals.

## Accessibility & Inclusion

- Status is never shown by colour alone; prayer states always carry a text label.
- Activity colours were checked for colour-blind safety in light and dark mode.
- Input text is 16px or larger (to stop iOS zooming on focus), and the layout respects safe-area insets.
- Light and dark mode both follow the system setting.
