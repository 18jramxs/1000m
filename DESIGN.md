---
name: 1000 m Tracker
description: Liquid Glass × Apple Fitness × Nike — mismo sistema visual que gym-tracker, aplicado al tracker de series/rodaje/velocidad + test mensual
colors:
  bg: "#050507"
  bg-card: "rgba(255,255,255,0.045)"
  bg-input: "rgba(255,255,255,0.06)"
  border: "rgba(255,255,255,0.08)"
  border-2: "rgba(255,255,255,0.14)"
  text-primary: "#ffffff"
  text-secondary: "rgba(255,255,255,0.62)"
  text-tertiary: "rgba(255,255,255,0.54)"
  blue: "#2979ff"
  blue2: "#6ea8ff"
  green: "#b6ff2e"
  red: "#ff453a"
  amber: "#ffd60a"
  orange: "#ff6b00"
typography:
  display:
    fontFamily: "Bebas Neue, Anton, SF Pro Display, system-ui, sans-serif"
    fontSize: "22px-44px"
    fontWeight: 400
    lineHeight: 1
    fontFeature: "uppercase"
  body:
    fontFamily: "-apple-system, BlinkMacSystemFont, SF Pro Text, Inter, Segoe UI, sans-serif"
    fontSize: "13px-15px"
    fontWeight: 400-700
  label:
    fontFamily: "-apple-system, BlinkMacSystemFont, SF Pro Text, sans-serif"
    fontSize: "9px-12.5px"
    fontWeight: 600-800
    letterSpacing: "0.3px-1.6px"
    fontFeature: "uppercase"
  mono-data:
    fontFamily: "SF Mono, ui-monospace, Roboto Mono, Menlo, monospace"
    fontSize: "11px-14px"
    fontWeight: 500-600
rounded:
  xs: "10px"
  sm: "14px"
  md: "20px"
  lg: "26px"
  pill: "100px"
spacing:
  screen-pad: "0 16px 8px"
  header-height: "56px"
components:
  save-cta:
    backgroundColor: "#ffffff"
    textColor: "#000000"
    typography: "{typography.display}"
    rounded: "{rounded.md}"
    padding: "16px"
    width: "100%"
  card-glass:
    backgroundColor: "{colors.bg-card}"
    textColor: "{colors.text-primary}"
    rounded: "{rounded.md}"
    padding: "16px"
  segmented-control-active:
    backgroundColor: "#ffffff"
    textColor: "#000000"
    rounded: "{rounded.sm}"
  settings-row:
    backgroundColor: "transparent"
    textColor: "{colors.text-primary}"
    padding: "13px 16px"
  bottom-nav:
    backgroundColor: "rgba(14,14,18,0.6)"
    rounded: "{rounded.pill}"
    position: "fixed, floating, bottom"
---

# Design System: 1000 m Tracker

## Overview

**Creative North Star: "The Family Glass" — the exact system shipped in `gym-tracker/index.html`, ported token-for-token, not reinvented.**

This is the second correction of this app's visual direction. The first rewrite (noviembre 2026 training-model change) mistakenly adopted `estudio`'s own visual language (`kit-componentes.html`: Archivo/Archivo Narrow, a shifting per-tab background halo, hand-drawn micro-radii). That was wrong: `estudio` keeps its own system; `1000m` and `gym-tracker` are the pair that share one, and the shared one is gym-tracker's — Bebas Neue, SF Mono, a static tri-color mesh background, a single fixed app header, and the floating pill bottom-nav with its spring-eased sliding indicator. Three pieces of the retired estudio-style skin were kept anyway because they had genuinely earned their place: the Físico screen's card layout (title row → big current value → recent-readings list → add-row), the Historial list's flat row-with-left-dot-and-chevron (rather than gym-tracker's own expandable session cards), and red as the color of the Ajustes "Eliminar" action.

The material is near-black frosted glass everywhere: translucent white-on-black cards (`--bg-card`) over a slow-drifting three-color radial mesh (blue/lime/orange), with a near-invisible dot-grain texture on top. Big numbers are the loudest thing on screen — the today-hero title, PR tiles, stat pills — in oversized Bebas Neue; everything administrative (dates, ppm, distances, table-like data) drops into small SF Mono. There is exactly one fixed header per screen and it never scrolls or duplicates; section titles inside content (e.g. "Datos"/"Preferencias"/"Peligro" in Ajustes) scroll with the page and are never a second fixed bar.

**Key Characteristics:**
- Near-black glass cards (`.glass`/`.fisico-block`/`.chart-wrap`) sharing one recipe: `--bg-card` fill, hairline border, `shadow-card`
- Bebas Neue oversized numerals for hero/stat/PR values; SF Mono for every logged or computed data point
- A single fixed `.app-header` per screen (never sticky, never duplicated) plus the floating pill bottom-nav with a spring-eased sliding indicator
- Selected/active states (segmented control, filter pills, day/type pickers) invert to solid white-on-black, never a tinted accent
- Static tri-color mesh background (blue/lime/orange) — no per-tab recoloring, no "halo" mechanic

## Colors

- **Blue** (`#2979ff`): series de ritmo — hero accents, chart line, dot. The closest thing to a "primary" color, same role gym-tracker gives blue.
- **Green/volt-lime** (`#b6ff2e`): rodaje base — same roles for that type; also gym-tracker's universal "success" accent (nav-indicator glow, import icon tint).
- **Orange** (`#ff6b00`): velocidad — same roles; also gym-tracker's tertiary/CSV-style accent.
- **Amber** (`#ffd60a`): test 1.000 — same roles; the test-evolution chart's line and target marker.
- **Red** (`#ff453a`): the one negative/destructive color — delete actions, the Peligro section, negative resumen deltas. This is the one color explicitly carried over from the estudio-style build rather than re-derived, because gym-tracker's own red is the same hue family and the user specifically named "el rojo de ELIMINAR" as worth keeping.
- **Void** (`#050507`) / **Card glass** (`rgba(255,255,255,0.045)`) / **Text ladder** (`#fff` / `.62` / `.54`): identical to gym-tracker's own tokens, unmodified.

### Named Rules
**The One-Header Rule.** Exactly one `.app-header` exists per screen render, `position:fixed`, solid `var(--bg)` fill, sized by `env(safe-area-inset-top)`. Any title that lives inside scrolling content (settings-group eyebrows, chart labels) is never fixed or sticky — it scrolls normally. Two headers fighting for the same strip of screen is the defect this rule exists to prevent.
**The Type-Owns-Its-Color Rule.** Each session type (series/rodaje/velocidad/test) keeps one fixed accent everywhere it appears (hero, dot, chart line) — colors never migrate to generic chrome, and there is no per-tab background recoloring.

## Typography

**Display Font:** Bebas Neue (fallback Anton, SF Pro Display) — ported verbatim from gym-tracker; this build's prior Archivo Narrow is retired.
**Body Font:** -apple-system / SF Pro Text
**Mono/Data Font:** SF Mono (fallback ui-monospace, Roboto Mono, Menlo)

### Hierarchy
- **Display** (400, 22–44px, uppercase): today-hero title (44px, the single largest text on Hoy), "Descanso"'s smaller non-hero variant (28px), PR/stat values (24px), plan-day titles (16px), few-points big numbers (26px).
- **Body** (400–700, 13–15px): row text, settings labels, button labels.
- **Label** (600–800, 9–12.5px, uppercase, letter-spacing 0.3–1.6px): the app-header title, section eyebrows, field column headers, chips.
- **Mono data** (500–600, 11–14px): every logged or derived value — dates, ppm, notación compacta, históricos, detail-row values. Identical in spirit to gym-tracker's own Data-Is-Mono convention.

### Named Rules
**The Data-Is-Mono Rule.** Any value the user logged or the app computed from logged data (times, dates, ppm, notación compacta, table cells) renders in SF Mono; Bebas Neue is reserved for headline-scale numbers and short uppercase labels, never dense data.

## Layout

Single-column mobile stack (`.wrap`, `max-width:460px`), top-padded by `env(safe-area-inset-top) + 56px` to clear the fixed header, bottom-padded `100px` to clear the floating nav. Screens toggle via `display:none`/`.active`; active screens are a `flex-direction:column` stack with a flat `14px` gap between cards — tighter than the retired estudio-style `22px`, matching gym-tracker's own screen rhythm (`padding:14px 16px 8px`). Grids are used only for symmetric repeaters: the 3-column PR/stat grid, the 2-column segmented control, and Planificación's 4-equal-column field grid per day block.

### Named Rules
**The Equal-Grid Rule (Planificación).** Every day block's field row is `grid-template-columns:repeat(4,1fr)` regardless of how many fields that day type actually needs — rodaje uses 2 of the 4 cells and leaves the other 2 as empty placeholder divs, so column 1 always starts at the same x-position across Lunes/Miércoles/Viernes blocks in the same week. Never give a day type with fewer fields a narrower or re-centered grid.

## Elevation & Depth

Tonal glass layering plus a small shadow vocabulary, identical to gym-tracker: `shadow-card` (default card rest state), `shadow-card-lg` (today-hero, bottom sheet, toast), `shadow-nav` (the floating bottom-nav only). The bottom-nav's sliding indicator carries an intentional colored glow (`0 0 16px -6px rgba(182,255,46,0.16)`) — a verbatim port of gym-tracker's own nav-indicator treatment, not a generic "AI glow" to be flattened.

## Shapes

Four radius steps, identical values and names to gym-tracker: `10px` (`--r-xs`, inputs), `14px` (`--r-sm`, small buttons/toggles), `20px` (`--r`, default cards and the primary CTA), `26px` (`--r-lg`, today-hero and the bottom-sheet's top corners), plus a `100px` pill for the nav and segmented controls. Borders are always 1px hairlines at `.08–.14` opacity.

## Components

### Buttons
- **Primary (`.cta`/`.save-btn`):** solid white fill, black Bebas Neue uppercase label, `20px` radius — used for "Registrar" and "+ Añadir semana". No colored glow, no per-type tinting (that was the retired estudio-style `btn-glow`); this is gym-tracker's own plain, confident CTA.
- **Segmented control (`.metric-row`/`.metric-btn`):** 2-equal-width buttons, active inverts to white-on-black — used for the Historial/Planificación switch at the top of the second tab.
- **Filter pills (`.hist-tabs`/`.hist-tab`):** horizontal-scroll pill row, active inverts to white-on-black — used for Historial's type filter.

### Cards
- **Default (`.glass`/`.fisico-block`/`.chart-wrap`):** `--bg-card` fill, hairline border, `20px` radius, `shadow-card`. One shared recipe for every card-like surface in the app.
- **Today-hero:** the one card that breaks the default recipe on purpose — `26px` radius, stronger blur, a ghost Bebas Neue watermark, a one-shot diagonal shine sweep on mount. Ported from gym-tracker's own `.today-hero`.

### Historial Row (kept from the retired estudio build)
Flat row — left color dot (session-type color) + title/sub stack + trailing chevron — opening a bottom sheet with the full detail, rather than gym-tracker's own inline-expanding session card. This is one of the three deliberately-kept estudio-style pieces; don't "fix" it back into a `.hist-session` expand-in-place pattern.

### Planificación Week (`.hist-session`/`.hist-hdr`/`.hist-body`, reused)
Each plan week reuses gym-tracker's own collapsible-session component verbatim (tap header to toggle, `›`/`⌄` chevron swap, `.hist-body.open`) rather than inventing a new collapse pattern — a week behaves exactly like a historial session, just with editable fields instead of read-only data. Exactly one week is open by default: whichever week contains today, or the next upcoming week if today falls outside the whole plan. Opening a week closes any other open week (one at a time). Adding a week clones the last week's values and opens the new one for editing.

### Físico Card (kept from the retired estudio build)
Title row → oversized current-value readout → recent-readings list → inline add-row (date + value + "+"). This content layout survived the gym-tracker re-theme because it was already solving the "what's my current X and its trend" problem well; only its visual tokens changed (Bebas Neue value, SF Mono history rows, gym-tracker card recipe).

### Settings Row (`.sett-group`/`.sett-row`/`.sett-icon`, ported)
Grouped by a small uppercase eyebrow title, one `.glass` card per group, rows separated by hairlines (never one card per row) — colored icon square + label + optional right-aligned mono state value. Fixed section order: **Datos** → **Preferencias** → **Peligro**, always last and visually separated. Planificación is no longer a settings section — it moved to its own apartado under the Historial tab.

## Do's and Don'ts

### Do:
- **Do** keep exactly one fixed `.app-header` per screen; any other title scrolls with its content, per the One-Header Rule.
- **Do** keep each session type's color fixed everywhere it appears — never reassign it to chrome, and never reintroduce per-tab background recoloring.
- **Do** render every logged/derived value in SF Mono, per the Data-Is-Mono Rule.
- **Do** give every Planificación day block the same 4-column grid regardless of how many fields it uses, per the Equal-Grid Rule.
- **Do** treat the nav-indicator's colored glow and the today-hero's shine sweep as intentional gym-tracker brand commitments, not defects to flatten.

### Don't:
- **Don't** reintroduce Archivo/Archivo Narrow, a shifting background halo, or any other piece of the retired estudio-style (`kit-componentes.html`) skin — that direction was a mistake for this app and is fully retired.
- **Don't** move Planificación back into Ajustes; it is its own apartado alongside Historial under the second tab.
- **Don't** give a day block with fewer fields (rodaje) a narrower or re-centered grid — empty placeholder cells keep every block's columns aligned.
- **Don't** convert the Historial row or the Físico card layout back to gym-tracker's own native patterns (expandable session, etc.) — those two pieces are deliberate, named exceptions kept from the retired build.
