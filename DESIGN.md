---
name: Life Log
description: A personal iOS daily tracker built to the Apple Fitness / Health craft bar.
colors:
  page: "#f2f2f7"
  card: "#ffffff"
  ink: "#0b0b0f"
  ink-secondary: "#55555c"
  muted: "#6c6c72"
  hairline: "rgba(60,60,67,.12)"
  card-line: "rgba(0,0,0,.05)"
  chip: "#ececf0"
  track: "#e9e9ee"
  none: "#d1d1d6"
  grey: "#8e8e93"
  accent: "#2a78d6"
  accent-fill: "#1f6cc9"
  water: "#2a78d6"
  prayer: "#0ca30c"
  quran: "#d98a00"
  creatine: "#7b5cd6"
  skincare: "#d6457f"
  habit: "#3d5afe"
  run: "#eb6834"
  run-fill: "#bd4f1d"
  run-ink: "#a84014"
  gym: "#1baf7a"
  gym-fill: "#0f7b54"
  foot-fill: "#4a3aa7"
  gym-ink: "#0b6e49"
  foot: "#4a3aa7"
  good: "#0ca30c"
  good-ink: "#0a7d0a"
  on-fill: "#0a7f0a"
  on-text: "#ffffff"
  warn: "#fab219"
  bad: "#d03b3b"
  bad-ink: "#b42e2e"
  miss-fill: "#d03b3b"
  banner: "#fff6e0"
typography:
  large-title:
    fontFamily: "-apple-system, BlinkMacSystemFont, \"SF Pro Text\", \"Segoe UI\", system-ui, sans-serif"
    fontSize: "34px"
    fontWeight: 700
    lineHeight: 1.05
    letterSpacing: "-0.025em"
  headline:
    fontFamily: "-apple-system, BlinkMacSystemFont, \"SF Pro Text\", \"Segoe UI\", system-ui, sans-serif"
    fontSize: "19px"
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: "-0.015em"
  title:
    fontFamily: "-apple-system, BlinkMacSystemFont, \"SF Pro Text\", \"Segoe UI\", system-ui, sans-serif"
    fontSize: "17px"
    fontWeight: 700
    letterSpacing: "-0.01em"
  body:
    fontFamily: "-apple-system, BlinkMacSystemFont, \"SF Pro Text\", \"Segoe UI\", system-ui, sans-serif"
    fontSize: "15px"
    fontWeight: 400
    lineHeight: 1.35
  row:
    fontFamily: "-apple-system, BlinkMacSystemFont, \"SF Pro Text\", \"Segoe UI\", system-ui, sans-serif"
    fontSize: "16px"
    fontWeight: 600
  label:
    fontFamily: "-apple-system, BlinkMacSystemFont, \"SF Pro Text\", \"Segoe UI\", system-ui, sans-serif"
    fontSize: "13px"
    fontWeight: 600
  numeral-display:
    fontFamily: "ui-rounded, \"SF Pro Rounded\", -apple-system, BlinkMacSystemFont, \"Segoe UI\", system-ui, sans-serif"
    fontSize: "40px"
    fontWeight: 800
    lineHeight: 1
    letterSpacing: "-0.035em"
    fontFeature: "\"tnum\""
  numeral-ring:
    fontFamily: "ui-rounded, \"SF Pro Rounded\", -apple-system, BlinkMacSystemFont, \"Segoe UI\", system-ui, sans-serif"
    fontSize: "28px"
    fontWeight: 800
    lineHeight: 1
    letterSpacing: "-0.03em"
    fontFeature: "\"tnum\""
  numeral-stat:
    fontFamily: "ui-rounded, \"SF Pro Rounded\", -apple-system, BlinkMacSystemFont, \"Segoe UI\", system-ui, sans-serif"
    fontSize: "22px"
    fontWeight: 800
    letterSpacing: "-0.02em"
    fontFeature: "\"tnum\""
rounded:
  icon-sm: "7px"
  icon-solid: "8px"
  icon: "9px"
  icon-lg: "11px"
  segment: "12px"
  field: "14px"
  banner: "16px"
  group: "18px"
  card: "22px"
  sheet: "26px"
  capsule: "34px"
  full: "999px"
spacing:
  xs: "6px"
  sm: "8px"
  row: "10px"
  md: "14px"
  gutter: "16px"
  hero: "18px"
  section: "22px"
components:
  card:
    backgroundColor: "{colors.card}"
    rounded: "{rounded.card}"
    padding: "16px"
  stat-tile:
    backgroundColor: "{colors.card}"
    rounded: "{rounded.group}"
    padding: "12px 13px"
  button-quick-add:
    backgroundColor: "{colors.accent-fill}"
    textColor: "#ffffff"
    typography: "{typography.row}"
    rounded: "{rounded.full}"
    height: "46px"
  button-chip:
    backgroundColor: "{colors.chip}"
    textColor: "{colors.ink}"
    rounded: "{rounded.full}"
    height: "46px"
    width: "46px"
  button-more:
    backgroundColor: "{colors.chip}"
    textColor: "{colors.ink}"
    rounded: "{rounded.field}"
    height: "44px"
  button-save:
    backgroundColor: "{colors.accent-fill}"
    textColor: "#ffffff"
    rounded: "{rounded.full}"
    height: "52px"
  button-save-run:
    backgroundColor: "{colors.run-fill}"
    textColor: "#ffffff"
  button-save-gym:
    backgroundColor: "{colors.gym-fill}"
    textColor: "#ffffff"
  segment-track:
    backgroundColor: "{colors.chip}"
    rounded: "{rounded.segment}"
    padding: "3px"
  segment-on-time:
    backgroundColor: "{colors.on-fill}"
    textColor: "{colors.on-text}"
    typography: "{typography.label}"
    padding: "8px 10px"
  segment-late:
    backgroundColor: "{colors.warn}"
    textColor: "#2b2100"
    typography: "{typography.label}"
    padding: "8px 10px"
  segment-missed:
    backgroundColor: "{colors.miss-fill}"
    textColor: "#ffffff"
    typography: "{typography.label}"
    padding: "8px 10px"
  pill-goal-hit:
    textColor: "{colors.good-ink}"
    typography: "{typography.label}"
    rounded: "{rounded.full}"
    padding: "4px 10px"
  settings-group:
    backgroundColor: "{colors.card}"
    rounded: "{rounded.group}"
  settings-row:
    textColor: "{colors.ink}"
    padding: "10px 14px"
    height: "52px"
  field:
    backgroundColor: "{colors.card}"
    rounded: "{rounded.field}"
    padding: "8px 14px"
  switch-off:
    backgroundColor: "{colors.none}"
    rounded: "{rounded.full}"
    width: "51px"
    height: "31px"
  switch-on:
    backgroundColor: "{colors.good}"
---

# Design System: Life Log

## Overview

**Creative North Star: "The Apple-Made Tracker"**

Life Log should look as if Apple had shipped it next to Fitness and Health. It uses the iOS grouped-list world without changes: a pale grouped background (pure black in dark mode), solid content cards, SF Pro text and SF Pro Rounded numerals. The craft bar is Apple Fitness / Health and Apple's iOS 26 apps. The system succeeds when nothing reads as "a web page imitating iOS". It fails in the half-finished version of this look: emoji headers, grey chips everywhere, one flat accent colour and 12px type.

The screen is dense but calm. One card holds one subject, every number is big and rounded, and each tracked thing keeps its own hue across the ring, its icon tile, its bars and its Summary tiles. Depth comes from solid cards on a tinted page. Liquid Glass is used only on floating controls (the capsule tab bar, the round header buttons and the top bar that appears on scroll), never on content.

The voice is firm accountability, and the visuals carry it. Misses are named in text ("Still open: …", "Missed"), use the same weight as hits and are never only a colour.

**Key Characteristics:**
- iOS grouped background with solid 22px cards that have a hairline border and a soft offset shadow.
- SF Pro text with rounded, tabular, heavy numerals for every quantity.
- One hue per tracked thing, used the same way everywhere.
- Drawn SVG glyphs in tinted rounded-square tiles; Settings uses solid tiles.
- Liquid Glass only on floating controls.
- Status is always a colour plus a text label.

## Colors

The palette is the iOS system palette applied per subject. Each tracked thing has its own colour, the neutrals are Apple's grouped greys, and a separate contrast-safe fill is defined wherever a colour has to carry white text. Every token has a dark-mode value, defined under `prefers-color-scheme: dark` and again under `:root[data-theme="dark"]`.

### Primary
- **System Blue** (accent / water): the interactive colour for links, focus rings, the active tab, the caret and "Add your own tracker". The same hue is water, so the most frequent action (logging water) uses the app's main colour.
- **Deep Press Blue** (accent-fill): the background behind white text on quick-add buttons, Save and the selected sheet type. It is darker than the accent so the white label passes contrast.

### Secondary (subject hues)
- **Prayer Green** (prayer): prayers. It shares its value with Good.
- **Quran Amber** (quran), **Creatine Violet** (creatine), **Skincare Pink** (skincare), **Habit Indigo** (habit, used for custom trackers): built-in and custom trackers.
- **Run Orange** (run) and **Gym Green** (gym): weekly activities. Each one has a darker **-fill** (behind white text) and a darker **-ink** (for coloured text on a tinted chip, such as the "+ Run" add button).
- **Football Indigo** (foot): football. It appears only where football was logged.

### Tertiary (status)
- **Good** / **Good Ink**: hits, the "Goal hit" pill, the ✓ mark and switches that are on.
- **On-Time Fill** with **On-Text**: the selected "On time" segment. In dark mode the fill is the bright green and the text turns near-black (#04210a).
- **Late Amber** (warn) with dark text #2b2100: the selected "Late" segment and the late band in charts.
- **Bad** / **Miss Fill** / **Bad Ink**: "Missed", the erase action and red text.
- **Not Logged** (none): empty segments in charts, the off switch and the sheet grabber.

### Neutral
- **Grouped Page** (page): the app background. It is #000000 in dark mode.
- **Card White** (card): every content surface. It is #1c1c1e in dark mode.
- **Ink**, **Ink Secondary** and **Muted**: primary text, secondary text and values, and chevrons.
- **Chip** and **Track**: secondary buttons, segment tracks and the empty part of a progress bar.
- **Hairline** (line) and **Card Line**: row dividers and card borders.
- **System Grey** (grey): the tile colour for utility rows (CSV export, Version). It is #636366 in dark mode.
- **Banner Cream** (banner): the background of the backup and install notices.

### Named Rules
**The Fill-Is-Not-The-Hue Rule.** Never put white text on a base subject hue. Text-bearing fills use the `-fill` tokens (`accent-fill`, `run-fill`, `gym-fill`, `foot-fill`, `on-fill`, `miss-fill`), and coloured text uses the `-ink` tokens (`run-ink`, `gym-ink`, `good-ink`, `bad-ink`). The base hues are for arcs, bars, dots and tinted tiles.

**The One Hue Per Thing Rule.** A tracked thing always uses the same colour on its ring arc, icon tile, bars, Summary tile and Settings row. Don't reassign it per screen.

**The Label-Always Rule.** Status is never shown by colour alone. Prayer segments say "On time", "Late" or "Missed". Hits carry a ✓ or "Goal hit". Misses on the goal ring are hollow dots with their name written out.

## Typography

**Display Font:** the system face (-apple-system / SF Pro Text, with Segoe UI and system-ui as fallbacks)
**Numeral Font:** SF Pro Rounded through `--round` (ui-rounded, falling back to the system face)

**Character:** SF Pro for words, set tight and confident in the iOS large-title style, and SF Pro Rounded at weight 800 for every number, so quantities read like the figures in Fitness.

### Hierarchy
- **Large Title** (700, 34px, 1.05, -0.025em): one per screen ("Today", "Summary", "Settings"), with the date or period beneath it at 15px/500 in secondary ink. It is mirrored in the 17px glass top bar on scroll.
- **Headline** (700, 19px, 1.2): the hero sentence ("2 of 5 daily goals") and the app card name.
- **Title** (700, 17px, -0.01em): card titles next to their icon tile.
- **Row** (500–600, 16px): prayer names, habit names, list rows and Settings rows.
- **Body** (400, 15px, 1.35): the base size. Notes and meta text are 13–14px in secondary ink.
- **Label** (600, 12.5–13px): segment text, pills, legends and tile labels. Chart axes are 12px.
- **Numerals** (800, rounded, tabular): 40px for the water amount, 28px inside the ring, 22px for steppers, streaks and tiles, 15px for week values. The unit sits beside the number in a smaller rounded 700 in secondary ink.

### Named Rules
**The Rounded Numbers Rule.** Every quantity a person reads as a score uses `--round` with tabular figures. Words never do.

**The Native Section Header Rule.** Uppercase text is used only for iOS grouped-list section headers in Settings (13px, 500, +0.04em, secondary ink, sitting above a group). It is never used as a kicker above a heading on a content card.

## Layout

The layout is a single centred column, at most 560px wide, with a 16px side gutter, safe-area top padding plus 14px, and 110px plus the safe area at the bottom so content clears the floating tab bar. Cards stack 14px apart. Card padding is 16px (18px on the hero). Rows inside a card use 10px vertical padding with hairline dividers between them. Header and card-title rows use 10–12px gaps, and button rows use 8px gaps.

Today follows the order of the first viewport: large title, the daily-goals hero (96px ring beside the sentence and key), Water, then Prayers. Summary opens with a Week / Month / Year segmented control and a two-column grid of stat tiles (10px gap). An odd last tile spans both columns. Settings is iOS grouped lists: section headers set 16px in from the group edge, rows at least 52px tall, and dividers inset to 56px so they start after the icon tile. Wide tables scroll sideways inside their card. There are no breakpoints: on a desktop the column simply stays centred at 560px, and the tab capsule caps at 380px.

## Elevation & Depth

This is a hybrid. Content is solid and very slightly raised; only floating controls are glass. In light mode a card lifts off the grouped page with a hairline border and a soft, downward-offset two-layer shadow. In dark mode that shadow is replaced by a faint inset top highlight, and depth comes from #1c1c1e cards on pure black. Glass (blur 22px, saturate 180%, a translucent fill, a bright 1px edge and an inner top highlight) floats above the content.

### Shadow Vocabulary
- **Card lift** (`box-shadow: 0 1px 2px rgba(16,24,40,.04), 0 6px 18px rgba(16,24,40,.05)`): cards, stat tiles, Settings groups and the app card in light mode. In dark mode it is `0 1px 0 rgba(255,255,255,.03) inset`.
- **Glass float** (`box-shadow: inset 0 1px 0 rgba(255,255,255,.85), 0 1px 1px rgba(0,0,0,.04), 0 10px 30px rgba(0,0,0,.12)`): the tab capsule. The round header buttons use the same recipe with a 0 4px 14px rgba(0,0,0,.08) drop.
- **Selected segment** (`box-shadow: 0 1px 3px rgba(0,0,0,.15)`): the chosen prayer segment and the active Summary period.
- **Sheet** (`box-shadow: 0 -10px 40px rgba(0,0,0,.15)`): bottom sheets. Toasts and tooltips use 0 6–8px 18–24px at .2.

### Named Rules
**The Glass-Floats-Only Rule.** Backdrop blur is allowed only on things that float over content: the tab capsule, the round ‹ › and "Today" header buttons, and the top bar that appears on scroll. Cards, tiles, sheets and Settings groups stay solid.

## Shapes

Shapes are continuous and soft, following iOS. Cards have 22px corners, stat tiles and Settings groups 18px, banners 16px, fields and the "Log another activity" bar 14px, segment tracks 12px with 9px thumbs, and sheets 26px on the top corners only. Icon tiles are rounded squares sized to their scale (30px tile, 9px radius; 36px tile, 11px radius; 24px tile, 7px radius; Settings solid tiles 30px with 8px radius). Every primary and secondary button is a full pill, and every round control is a true circle (40px header buttons, 36px steppers, 30px delete buttons). Progress bars are 10px tall with 5px rounding (7px tall in This week). Chart bars round only their top corners.

## Components

### Buttons
Buttons are tactile, full-pill shapes that react to the finger.
- **Shape:** full pill (46px tall on cards, 52px for Save).
- **Primary (quick-add water):** accent-fill with white rounded numerals at 16/700, shown three across ("+250 / +500 / +750").
- **Secondary (icon only):** 46px chip circles for "other amount" and "undo".
- **Add (tinted):** a 34px pill with the subject's hue at tint opacity behind it and its `-ink` colour on the label ("+ Run", "+ Gym").
- **Save:** a full-width 52px pill in accent-fill, or run-fill / gym-fill / foot-fill on those sheets.
- **Press:** everything tappable scales to 0.94 on `:active` with a 0.2s cubic-bezier(.2,.8,.2,1). Focus is a 2px accent outline offset 2px.

### Segmented controls
- **Prayer segment:** a chip track (12px, 3px padding) with three text options. The selected option fills with its status (on-fill + on-text, warn + #2b2100, or miss-fill + white) and gains the selected-segment shadow. Fill and text colour transition over 0.2s.
- **Period control (Summary):** a chip2 track whose selected option is a raised white thumb (#48484e in dark mode). This is the iOS segmented control.

### Cards / Containers
- **Corner Style:** 22px.
- **Background:** card.
- **Shadow Strategy:** card lift (see Elevation & Depth).
- **Border:** a 1px card-line hairline.
- **Internal Padding:** 16px (18px on the hero). The header row is an icon tile plus a 17px title on the left and secondary text or a status pill on the right.

### Icon tiles
A signature of the system: drawn SVG glyphs (one stroke family, 24-unit grid) sitting in rounded-square tiles coloured with the subject hue.
- **Tinted (default):** the glyph is in the hue, and the tile behind it is the same hue at `--tint-a` (13% light, 20% dark). Card headers, rows and tiles use it.
- **Solid (Settings):** a white glyph on a full-strength tile, like iOS Settings. Utility rows use System Grey.
- **Sizes:** xs 22, sm 24, default 30, lg 36.

### Inputs / Fields
- **Style:** a card-coloured block with a 1px hairline and 14px corners. A 12.5px label sits above a 20px/700 rounded value. Inputs are always at least 16px.
- **Focus:** the border turns accent with a 3px accent-soft ring.
- **Switch:** the iOS switch (51×31). It is grey (none) when off and good when on, with a white knob that slides over 0.3s.

### Navigation
- **Tab bar:** a floating glass capsule (radius 34px, max width 380px) above the home indicator, with three tabs (filled SVG glyph above an 11px/600 label). The active tab turns accent, and a translucent bubble springs under it.
- **Header:** the large title on the left; glass ‹ › circles on the right, plus a glass "Today" pill when viewing another day.
- **Top bar:** a full-width glass strip that fades in after 56px of scroll and repeats the screen title at 17px.

### Daily-goals ring (signature)
A 96px ring split into one arc per daily goal, with gaps between arcs. Each arc shows its subject hue at 20% as the track and fills in full hue. The count (28px rounded) sits in the middle with "goals" under it. Beside it is a 19px sentence, a "Still open: …" or "Missed: …" line naming the open goals in bold, and a key of dots: filled for hit, hollow rings for open.

### Summary data cards
Each card is a standard card with an icon-tile title and a right-aligned secondary note. Charts are hand-drawn SVG in a 320-wide viewBox, with 12px axis labels, 13px row labels and 12px rounded tabular values. Hairline gridlines are drawn at 0.6 width.
- **Comparison badge:** a 12px/700 pill under each tile's goal line. An arrow icon plus "Oct: 15/23 days" shows the earlier period's value in the tile's own unit.
  - The direction comes from rates, not raw totals.
  - Week Runs and Gym compare against last week up to the same weekday ("Last week by Wed").
  - Colours: up uses good-ink on a good tint, down uses bad-ink on a bad tint, and flat uses chip.
- **Weekday heatmap:** prayer rows by Mon–Sun columns plus an outlined "All" column. Each cell is the prayer hue mixed into the track by its on-time %, showing the % in rounded 800. High cells use `--hm-hi` dark text. A red callout names the weakest slot.
- **Callout:** a 14px/600 bad-ink sentence on a 10% bad tint with a warning icon. It is how the app states a slip plainly ("Fajr slips most on Saturdays: 40% on time.", "Last lower-body session: 19 days ago.").
- **Stat chips:** well-coloured 14px-radius blocks with a 20px rounded value and a 12.5px label, in rows of two or three. They are used for drink stats and all-time bests.
- **Curves and scatter:**
  - When you drink is a water-hue line over a 14% fill against a dashed ink2 steady-pace line. Point labels carry a card-coloured paint-order halo.
  - Run pace is a run-hue scatter (faster = higher) with a 45%-opacity trend line. The latest run is drawn as a larger dot with a card ring, and its value appears in the note.
- **Record bars:** an 8px track with the current streak filled in the subject hue, measured against the all-time best. A "Record" good pill marks a streak that is at its best.
- **Year at a glance:** 12 mini month grids, 4 across. Each day cell is a 2px-radius square mixed from good by the share of daily goals hit; untracked days are a faded track.
- **Gym split:** one gym-green family (gym-fill, a darker gym-fill mix, and a light gym mix with ink text). The split never borrows run or football hues.

### Motion
Re-rendering keeps state: `render()` carries each `[data-k]` element's previous class and style across the redraw and then restores the new ones, so ring arcs (0.6s), bars (0.4s), segment fills and switches animate instead of jumping. The standard ease is cubic-bezier(.2,.8,.2,1). Sheets rise over 0.35s with cubic-bezier(.2,.9,.25,1). Reduced motion sets every transition to 0s.

**The One Spring Rule.** The tab bubble's cubic-bezier(.3,1.35,.5,1) over 0.45s is the only overshoot in the app. Everything else settles without bouncing.

## Do's and Don'ts

### Do:
- **Do** put every content block in a solid card: 22px radius, card-line hairline, card lift shadow.
- **Do** set every score, amount and count in `--round` at weight 800 with tabular figures.
- **Do** give each tracked thing one hue and use it the same way on its ring arc, tinted icon tile, bars and tiles.
- **Do** use a `-fill` token behind white text and an `-ink` token for coloured text on a tint.
- **Do** pair every status colour with a word or a ✓ ("On time", "Late", "Missed", "Goal hit").
- **Do** draw icons as inline SVG inside an icon tile: tinted on content, solid in Settings.
- **Do** keep football out of Today's This week and Streaks. It is logged through "Log another activity" and appears in Summary only for periods where it was played.

### Don't:
- **Don't** put backdrop blur or glass on cards, tiles, sheets or Settings groups. Glass floats only.
- **Don't** put white text on a base subject hue (water, run, gym, prayer).
- **Don't** add a second spring or bounce. The tab bubble owns the only overshoot.
- **Don't** use emoji as headers or icons on built-in surfaces.
- **Don't** add uppercase kickers or eyebrows above titles. Uppercase belongs only to Settings section headers.
- **Don't** soften or hide a miss. Name it in text with the same weight as a hit.
