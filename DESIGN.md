---
name: 1000 m Tracker
description: Near-black liquid-glass running log that turns a stopwatch time into the Policía Nacional 1000m baremo score
colors:
  bg-void: "#050507"
  bg-void-2: "#0a0a0c"
  card-glass: "rgba(255,255,255,0.045)"
  card-glass-strong: "rgba(20,20,26,0.55)"
  border-hairline: "rgba(255,255,255,0.08)"
  border-hairline-2: "rgba(255,255,255,0.14)"
  border-hairline-3: "rgba(255,255,255,0.22)"
  text-primary: "#ffffff"
  text-secondary: "rgba(255,255,255,0.62)"
  text-tertiary: "rgba(255,255,255,0.54)"
  text-ghost: "rgba(255,255,255,0.18)"
  blue-cta: "#2979ff"
  blue-cta-light: "#6ea8ff"
  blue-cta-highlight: "#3989ff"
  blue-cta-deep: "#1f6ce8"
  volt-lime: "#b6ff2e"
  signal-red: "#ff453a"
  baremo-amber: "#ffd60a"
  ember-orange: "#ff6b00"
  series-pink: "#ff2d92"
  ink-black: "#000000"
typography:
  backdrop-ghost:
    fontFamily: "Bebas Neue, Anton, SF Pro Display, system-ui, sans-serif"
    fontSize: "96px"
    fontWeight: 400
    lineHeight: 0.85
    letterSpacing: "-1px"
  headline-display:
    fontFamily: "Bebas Neue, Anton, SF Pro Display, system-ui, sans-serif"
    fontSize: "52px"
    fontWeight: 400
    lineHeight: 1
    letterSpacing: "0"
  display:
    fontFamily: "Bebas Neue, Anton, SF Pro Display, system-ui, sans-serif"
    fontSize: "38px"
    fontWeight: 400
    lineHeight: 1
    letterSpacing: "0"
  value-display:
    fontFamily: "Bebas Neue, Anton, SF Pro Display, system-ui, sans-serif"
    fontSize: "18px-24px"
    fontWeight: 400
    lineHeight: 1
  label-display:
    fontFamily: "Bebas Neue, Anton, SF Pro Display, system-ui, sans-serif"
    fontSize: "14px-22px"
    fontWeight: 400
    lineHeight: 1.15
    letterSpacing: "0.4px"
    fontFeature: "uppercase"
  body:
    fontFamily: "-apple-system, BlinkMacSystemFont, SF Pro Text, Inter, Segoe UI, sans-serif"
    fontSize: "15px"
    fontWeight: 400
    lineHeight: 1.4
  label:
    fontFamily: "-apple-system, BlinkMacSystemFont, SF Pro Text, Inter, Segoe UI, sans-serif"
    fontSize: "9px-11px"
    fontWeight: 600
    letterSpacing: "0.4px-0.7px"
    fontFeature: "uppercase"
  mono-data:
    fontFamily: "SF Mono, ui-monospace, Roboto Mono, Menlo, monospace"
    fontSize: "10px-14px"
    fontWeight: 500
rounded:
  hairline: "1px"
  swatch: "2px"
  dot: "3px"
  badge: "6px"
  day-cell: "8px"
  xs: "10px"
  settings-icon: "11px"
  icon-tile: "12px"
  sm: "14px"
  md: "20px"
  lg: "26px"
  pill: "100px"
spacing:
  xs: "6px"
  sm: "8px"
  md: "12px"
  lg: "16px"
  xl: "20px"
  screen-pad: "14px 16px 8px"
components:
  save-cta:
    backgroundColor: "linear-gradient(180deg, #3989ff 0%, #2979ff 50%, #1f6ce8 100%)"
    textColor: "#ffffff"
    typography: "{typography.label-display}"
    rounded: "{rounded.md}"
    padding: "16px"
    width: "100%"
  type-picker-selected:
    backgroundColor: "#ffffff"
    textColor: "#000000"
    typography: "{typography.label-display}"
    rounded: "{rounded.sm}"
    padding: "12px 2px"
  type-picker-default:
    backgroundColor: "rgba(255,255,255,0.04)"
    textColor: "{colors.text-secondary}"
    typography: "{typography.label-display}"
    rounded: "{rounded.sm}"
    padding: "12px 2px"
  card-glass:
    backgroundColor: "{colors.card-glass}"
    textColor: "{colors.text-primary}"
    rounded: "{rounded.md}"
    padding: "16px"
  nav-pill:
    backgroundColor: "rgba(14,14,18,0.6)"
    textColor: "{colors.text-tertiary}"
    rounded: "{rounded.pill}"
    padding: "6px"
---

# Design System: 1000 m Tracker

## Overview

**Creative North Star: "The Family Glass" — a near-black Liquid Glass instrument shared verbatim with gym-tracker, reskinned onto 1000m's own content, not reinvented for it.**

This is not an organic system that evolved on its own project; it is a deliberate, token-for-token port of gym-tracker's shipped CSS (colors, Bebas Neue + SF Mono type pairing, the glass-card recipe with its glossy top-edge highlight, the pill bottom-nav with a single sliding indicator, the today-hero pattern, the activity-map calendar, the bottom-sheet modal, the blue-glow save CTA) reapplied to a different domain: series cortas/largas, rodaje, timed 1000m tests, and baremo scoring. The two apps are used by the same person preparing for the same Policía Nacional physical exam, and they are meant to read as one family wearing two outfits of the same cut. Where this build's own content diverges from gym-tracker's (an amber baremo accent, a pink series-largas badge, the activity-map's trained/rest legend), those are genuine 1000m-specific extensions of the shared vocabulary, not departures from it.

The material is near-black frosted glass at every surface: translucent white-on-black cards with heavy backdrop blur, a slow-drifting radial-gradient mesh behind everything, and a near-invisible dot-grain texture over the whole viewport. Numbers are the loudest thing on screen — oversized Bebas Neue for hero titles, stat tiles, and the 2:55 objective card — while everything administrative (labels, timestamps, table data) drops into small-caps SF Mono. Motion is springy and confident (a spring-eased sliding nav indicator, a one-shot shine sweep across the today-hero, snappy button-press scale-downs) rather than flat or restrained.

**Key Characteristics:**
- Near-black glass surfaces with a glossy top-edge highlight on every card
- Bebas Neue oversized numerals for hero data; SF Mono for administrative/tabular data
- A single blue CTA color, reserved for the primary save action and the current-baremo row
- Selected/active states invert to solid white-on-black rather than tinting the accent color
- Pill bottom-nav with one spring-eased sliding indicator shared verbatim with gym-tracker

## Colors

Near-black glass base with a small, disciplined accent set: one CTA blue, one success/volt-lime, one baremo amber, plus orange/pink used only for scoped category badges.

### Primary
- **Blue CTA** (#2979ff): the save-session button gradient, focus rings, the "current" row highlight in the baremo table, and the cortas type-badge. The only color that means "act on this."
- **Blue CTA Light** (#6ea8ff): text-on-blue-bg contexts (test-banner strong text, current-baremo row text, active nav-icon glow).

### Secondary
- **Volt Lime** (#b6ff2e): success/positive state only — the header pulse dot, "trained" days on the activity-map, the rodaje type-badge, PR/record highlights, target-score row in the baremo table.
- **Baremo Amber** (#ffd60a): reserved for baremo/scoring content specifically — the objetivo-final card (2:55 target), personal-record values, the test type-badge, the monthly-test section icon.

### Tertiary
- **Ember Orange** (#ff6b00): scoped to the objetivo-card's gradient partner and the CSV-export icon; never a standalone accent.
- **Series Pink** (#ff2d92): scoped to the series-largas type-badge and the baremo-table section icon; a single category color, not reused elsewhere.
- **Signal Red** (#ff453a): destructive/negative only — delete buttons, "rest day" on the activity-map, danger settings row.

### Neutral
- **Void Black** (#050507): the page background; nothing sits directly on pure black, everything sits on a glass card above it.
- **Card Glass** (rgba(255,255,255,0.045)): the base card fill, layered as a gradient with lighter/darker stops, never a flat color.
- **Hairline Border** (rgba(255,255,255,0.08)): the default 1px card/divider border.
- **Text Primary** (#ffffff): headings and primary values.
- **Text Secondary** (rgba(255,255,255,0.62)): body copy, unselected nav/type labels.
- **Text Tertiary** (rgba(255,255,255,0.54)): captions, section subtitles, table labels.

### Named Rules
**The One CTA Rule.** Blue is the only color that means "primary action." It appears on the save button and the "this is where you are now" baremo row — nowhere else does an interactive element use blue as its resting fill.

**The Invert-to-White Rule.** Selected/active states (type picker, filter chips, progress-period pills, primary modal button) do not tint toward the accent color; they invert to solid white background with black text. Category color (blue/green/pink/amber) is reserved for passive badges and data, never for the selected-state fill itself.

## Typography

**Display Font:** Bebas Neue (fallback Anton, SF Pro Display, system-ui)
**Body Font:** -apple-system / SF Pro Text (fallback Inter, Segoe UI)
**Label/Mono Font:** SF Mono (fallback ui-monospace, Roboto Mono, Menlo)

**Character:** A tall, condensed display face for anything that is a number or a headline — times, scores, section titles in buttons — paired against a neutral system sans for prose and a monospace for anything tabular or timestamp-like, so the eye can tell "this is data to read carefully" from "this is a headline" at a glance.

### Hierarchy
- **Display / Headline** (400, 38–52px, line-height 1): the today-hero title and the objetivo-final "2:55" — the single largest number on any given screen.
- **Title (label-display)** (400, 14–22px, uppercase, line-height 1.15): type-picker buttons, filter chips, modal titles, stat-tile values (22–24px) — anywhere a short label or number needs display-face weight without hero size.
- **Body** (400, 15px, line-height ~1.4): default running text, settings row labels.
- **Label** (600, 9.5–11px, uppercase, letter-spacing 0.4–0.7px): tile captions, section subtitles-as-labels, badge text.
- **Mono data** (500–700, 12–14px): anything that is a logged value, date, or table cell — block-value, history-row-val, baremo-table cells, test-info values.

### Named Rules
**The Data-Is-Mono Rule.** Any value the user logged or that the app computed from logged data (times, dates, distances, table rows) renders in SF Mono. Bebas Neue is reserved for headline-scale numbers and short button/chip labels; it never carries dense tabular data.

## Layout

Single-column mobile-first stack, `max-width` implicitly the viewport (no desktop breakpoint observed — this is a phone-first PWA). Screens live in `.screen` panels toggled via `display:none`/`.active`, padded `14px 16px 8px`. Cards stack vertically with a consistent `10–14px` bottom margin. Grids are used only for symmetric repeaters: the 3-column type picker, the 3-column stat tiles, the 2-column records grid, and the 7-column activity-map week row. The bottom nav is a fixed pill floating `18px` off the bottom edge, not a full-width bar — content gets `100px` of bottom padding to clear it.

## Elevation & Depth

Hybrid: tonal glass layering does most of the depth work (translucent gradient fills + backdrop blur create surface separation), with a small, consistent shadow vocabulary reinforcing which layer floats highest. Nothing outside the header/nav/hero/modal/toast tier gets a shadow — ordinary cards rely on their border + glass fill alone.

### Shadow Vocabulary
- **shadow-card** (`0 8px 24px rgba(0,0,0,0.35), inset 0 1px 0 rgba(255,255,255,0.06)`): default card elevation.
- **shadow-card-lg** (`0 18px 50px rgba(0,0,0,0.55), inset 0 1px 0 rgba(255,255,255,0.08)`): the today-hero, modal sheet, and toast — the highest-attention surfaces.
- **shadow-nav** (`0 14px 40px rgba(0,0,0,0.55), inset 0 1px 0 rgba(255,255,255,0.08)`): the floating bottom-nav pill only.

### Named Rules
**The Glossy Top-Edge Rule.** Every glass card (`.fisico-card`, `.block-card`, `.history-session`, `.session-info`, `.settings-group`) carries a 1px horizontal highlight line inset 8% from each edge at its very top (`::after` with a transparent→white→transparent gradient), simulating a light catching the top rim of a glass panel. This is the one universal card signature — apply it to any new card-like surface.

## Shapes

Radius is generous and consistent across four steps: `10px` (inputs, small chips), `14px` (buttons, icon tiles), `20px` (default cards, the save CTA), `26px` (hero cards, modal sheet top corners), and a `100px` pill for nav, chips, and filter/period selectors. Borders are always 1px hairlines at low opacity (never a solid saturated stroke). Corners never mix radii within one component. The bottom-sheet modal is the one shape that breaks bilateral symmetry on purpose: rounded top corners only (`26px 26px 0 0`), flush to the bottom edge.

## Components

### Buttons
- **Shape:** pill (`100px`) for filters/period selectors and the drag-handle-topped modal actions; `14–20px` rounded rect for the save CTA, add-buttons, and type-picker cells.
- **Primary (save CTA):** blue vertical gradient (`#3989ff → #2979ff → #1f6ce8`), white Bebas Neue label, full width, `16px` padding, blue-tinted glow shadow.
- **Hover/Focus:** press states scale down (`0.95–0.985`) with the shared spring-pop easing; no separate hover state is designed (touch-first product).
- **Secondary/Ghost:** `rgba(255,255,255,0.04–0.06)` fill, hairline border, secondary text color — used for add-buttons, nav-arrow circles, modal secondary action.

### Chips
- **Style:** pill shape, `rgba(255,255,255,0.04)` fill, hairline border, secondary text, Bebas Neue label for filter chips (uppercase) or system sans for period pills.
- **State:** selected/active inverts to white fill + black text (see Invert-to-White Rule); unselected stays transparent-glass.

### Cards / Containers
- **Corner Style:** `20px` default, `26px` for hero/modal.
- **Background:** layered gradient glass fill (`rgba(255,255,255,0.055→0.018→0.03)`), never a flat color.
- **Shadow Strategy:** `shadow-card` at rest; `shadow-card-lg` for the today-hero and modal only.
- **Border:** 1px hairline, plus the glossy top-edge accent line.
- **Internal Padding:** section-header/body split at `16px` horizontal, or a flat `14px` for simple content cards.

### Inputs / Fields
- **Style:** `rgba(255,255,255,0.06)` fill, hairline border, `10px` radius, SF Mono for numeric fields.
- **Focus:** border brightens to `border-3` opacity plus a blue glow ring (`0 0 0 3px rgba(41,121,255,0.18)`).

### Navigation
- **Style:** floating pill bar, `18px` off the bottom edge, glass fill with strong blur, one absolutely-positioned sliding indicator (`.nav-indicator`) that moves via `transform`/`width` transition on a spring easing (`cubic-bezier(0.34,1.56,0.64,1)`), carrying a faint volt-lime-tinted glow shadow.
- **Icons:** inline stroke SVGs (not a glyph icon font), `currentColor`, active icon gets a soft blue drop-shadow.
- **States:** active label goes to full white; inactive stays `text3`. Press scales to `0.92`.

### Today-Hero (signature component)
The opening screen's anchor: a large glass card with an oversized ghost-text watermark in the background, a Bebas Neue title, a one-shot diagonal shine sweep on mount, and a 2-tile stat row (next test countdown / current baremo score) below the title — not above it as a kicker. This is the first thing the user sees and it must answer "what am I doing, when's my next test, what's my score" without any interaction.

### Activity-Map Calendar (signature component)
A 7-column week-grid calendar reused from gym-tracker's pattern: each day cell is a small rounded square, solid volt-lime when trained, solid red when rest, dim ghost fill for future days. No text inside cells beyond the day number in mono.

## Do's and Don'ts

### Do:
- **Do** keep Bebas Neue reserved for headline-scale numbers, hero titles, and short uppercase button/chip labels — never body copy or dense data.
- **Do** render every logged/computed value (times, dates, table cells) in SF Mono, per the Data-Is-Mono Rule.
- **Do** apply the glossy top-edge highlight to any new card-like surface, per the Glossy Top-Edge Rule.
- **Do** treat the spring-eased sliding nav indicator, its colored glow shadow, and the subtle full-viewport grain texture as intentional shared brand commitments with gym-tracker — not defects to "fix" by flattening them.
- **Do** put contextual info (day/date, status) in a row *below* a card's title, not above it.

### Don't:
- **Don't** add a kicker or eyebrow label above any heading (e.g. a small "Hoy" caption sitting above the today-hero's title). Gym-tracker's own incumbent `.today-hero` does this; this build deliberately did not port it, because a kicker/eyebrow above a heading is an absolute craft-floor ban that no brief overrides. This is a defect carried by gym-tracker's build, not a pattern to reproduce here or reintroduce there.
- **Don't** tint a selected/active state toward its category accent color — invert to solid white-on-black instead, per the Invert-to-White Rule.
- **Don't** give an ordinary content card its own drop shadow; shadows are reserved for the header, nav, hero, modal, and toast tier only.
- **Don't** introduce a second CTA color; blue stays the only "act on this" signal on screen.
