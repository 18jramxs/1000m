---
name: KM Tracker
description: Liquid Glass × Apple Fitness × Nike — mismo sistema visual que gym-tracker, componentes reales reutilizados tal cual (cabecera, today-hero, day-grid, profile-card, emom-card)
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
  ink-black: "#000000"
  overlay-black: "rgba(0,0,0,0.6)"
  shadow-black: "rgba(0,0,0,0.3)"
  emom-ink: "#111111"
  avatar-sky: "#cfe0ff"
  avatar-sky-deep: "#a9c6ff"
  avatar-ink: "#0a1224"
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
  chip: "6px"
  icon-tile: "11px"
  sec-icon-tile: "12px"
  seam: "1px"
  tip: "2px-5px"
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

# Design System: KM Tracker

## Overview

**Creative North Star: "The Family Glass" — the exact system shipped in `gym-tracker/index.html`, ported token-for-token, not reinvented.**

This app, formerly "1000 m Tracker," is now **KM Tracker**. This is the third correction of its visual direction, and this time the brief was explicit: don't approximate gym-tracker's system, open its real `index.html` and copy the real CSS and markup. `estudio` keeps its own system, untouched; `1000m`/`KM Tracker` and `gym-tracker` are the pair that share one, and the shared one is gym-tracker's — literally, component by component: the same `.header` (CNP badge + centered-ish title + mono accent name), the same `.today-hero` (ghost watermark, oversized Bebas Neue title, shine sweep, date pill), the same `.day-grid`/`.day-btn` picker (now LUN/MIÉ/VIE instead of gym's five training days), the same `.vol-info-btn` access row, the same `.emom-card` quick-register pattern (now logging rep times instead of EMOM dominadas), the same `.profile-card`/`.pstat` (FC máx/FC reposo/Peso in place of peso/grasa/magra), the same `.etapa-badge` chips (now the five HR zones), and the same macros-style detail card (now FC máx/FC reposo/Peso history+add). Two pieces of the earlier estudio-style build survive, re-skinned onto gym-tracker tokens, because the user explicitly asked to keep them: the Sesiones list's flat row-with-left-dot-and-chevron (rather than gym-tracker's own expandable session card), and red as the color of the Ajustes "Eliminar" action.

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
- **Ink black** (`#000000`): the text color on every inverted "selected/active/primary" surface — `.save-btn`, `.metric-btn.active`, `.hist-tab.active`, `.toggle-row button[aria-pressed="true"]`, `.sheet-actions .primary`. Always paired with a white fill, never used standalone; this is gym-tracker's own invert-to-white convention, reproduced verbatim at every one of its call sites.
- **Overlay black** (`rgba(0,0,0,0.6)`) / **Shadow black** (`rgba(0,0,0,0.3)`): the bottom-sheet backdrop and the nav-indicator's ambient shadow component respectively — both literal gym-tracker values, not new additions.
- **Emom ink** (`#111111`): the text color on `.emom-action` (the amber/orange "Guardar" gradient button) — gym-tracker's own near-black, not pure `#000`, chosen there so dark text doesn't look flat against a warm gradient.
- **Avatar sky / Avatar sky deep / Avatar ink** (`#cfe0ff` / `#a9c6ff` / `#0a1224`): the three stops of `.profile-av`'s diagonal gradient and its initial's text color — literal gym-tracker values for the profile avatar, unrelated to the session-type palette.

### Named Rules
**The Invert-to-White Rule.** Every selected/active/primary surface (segmented control, filter pills, toggle rows, the save CTA, the primary sheet action) inverts to solid white fill + ink-black text rather than tinting toward an accent color — ported verbatim from gym-tracker, where this is the one universal "this is chosen/primary" signal.

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

Tonal glass layering plus a small shadow vocabulary, identical to gym-tracker: `shadow-card` (default card rest state), `shadow-card-lg` (today-hero, bottom sheet, toast), `shadow-nav` (the floating bottom-nav only). The bottom-nav's sliding indicator carries an intentional colored glow (`0 0 16px -6px rgba(182,255,46,0.16)`) — a verbatim port of gym-tracker's own nav-indicator treatment, not a generic "AI glow" to be flattened. That same indicator also transitions its `width` alongside `transform` (`cubic-bezier(0.34,1.56,0.64,1)`, a deliberately springy/bounce curve) — both the bounce easing and the width animation are literal gym-tracker source, needed because the pill must resize to match whichever nav button it's sliding under, not just translate. The faint fixed dot-grain (`body::after`, `radial-gradient(... 1px, transparent 1px)` tiled `3px 3px`) is gym-tracker's own "kill the banding" texture, also ported verbatim — not a decorative grid to be removed.

## Shapes

Four radius steps, identical values and names to gym-tracker: `10px` (`--r-xs`, inputs), `14px` (`--r-sm`, small buttons/toggles), `20px` (`--r`, default cards and the primary CTA), `26px` (`--r-lg`, today-hero and the bottom-sheet's top corners), plus a `100px` pill for the nav and segmented controls. Borders are always 1px hairlines at `.08–.14` opacity. Several more values are literal gym-tracker tokens kept outside that main scale because gym-tracker itself keeps them outside it: `6px` (`.hist-chip`), `11px` (the settings-row icon-tile square, `.sett-icon`), `12px` (the larger `sec-hdr` icon-tile, `.sec-icon` — used on Físico's profile/zonas/macro cards, a size step up from `.sett-icon` in the real gym-tracker file), `1px` (the glossy top-edge seam's own corner rounding, `.card::after{border-radius:1px}`), and a `2px–5px` "tip" range for decorative micro-details sized to their own element's height — the bar-chart taper, the caída-de-series progress-pill (`5px`), and the bottom-sheet's drag handle (`3px` on a `36×5px` bar).

## Components

### Header (`.header`, ported verbatim)
`<span class="cnp-badge">CNP</span>` + `<h1>KM TRACKER&nbsp;&nbsp;<span class="accent">jramxs</span></h1>`, `position:sticky;top:0`, the exact gradient-fade-to-transparent background, `env(safe-area-inset-top)`-aware padding. This is gym-tracker's literal header markup and CSS with only the title string changed. There is exactly one of these; nothing else in the app is a second fixed/sticky header.

### Today-Hero (`.today-hero`, ported verbatim)
Ghost Bebas Neue watermark (`.today-bg-text`) behind an oversized title (`.today-title`, the session type), a `.today-sub` line carrying the compact notación (tap to flip pace/time), the pitidos affordance, and a read-only date pill (`.date-input-label`) in a `.today-date-row`. One-shot diagonal shine sweep on mount, same timing as gym-tracker. On a rest day the same card shows a smaller (32px) title and a plain date line — rest is explicitly not the hero's full-size content.

### Day Picker (`.day-grid`/`.day-btn`, ported verbatim)
Same cells, radius, border, press-scale, and `.selected`/`.today` treatment as gym-tracker's five-day picker, just three cells (LUN/MIÉ/VIE) instead of five. Tapping a day opens its `openRegistro` sheet directly — a genuine capability gained from reusing this component, not just a visual match.

### Access Row (`.vol-info-btn`, ported verbatim)
Icon (stroke SVG, blue) + label + trailing chevron, one full-width row — "Resumen de la semana" here, "Volumen por grupo muscular" in gym-tracker. Opens a sheet with the week's Lun/Mié/Vie status, reusing `renderEstaSemanaBox`.

### Quick-Register Card (`.emom-card`, ported verbatim)
Amber-tinted header + body, used for series/velocidad days only (where "one more time" is a meaningful unit, same as gym-tracker's dominadas-rep-counter use of this component). A text input + green `.sign-btn.pos` ("+") appends a parsed time to an in-memory list, rendered as removable chips; the amber-glow `.emom-action` ("Guardar") commits them as that day's `tiempos`. A `.semana-card` row below shows the week's total meters. A small "Editar detalles" link still opens the full `openRegistro` sheet for FC/cadencia/sensación/notas — no field from the old single-sheet flow was removed, this card is a faster path to the one field (tiempos) that's logged most often.

### Profile Card (`.profile-card`/`.pstat`, ported verbatim)
Avatar with its blue inset glow, name, two `.pchip` pills (objetivo + best test or next test date), then a 3-column `.profile-stats` grid — FC máx / FC reposo / Peso instead of gym-tracker's peso/grasa/magra, each `.pstat` keeping the colored 2px bar-above-the-number (`.pstat::before`) in a type color (red/blue/green) rather than gym's grasa-amber/magra-red.

### Zonas Card (`.etapa-badge`, ported verbatim)
Same `sec-hdr`/`sec-body` card shape as gym-tracker's "Etapa actual," with each of the five HR zones as its own colored pill chip (`.etapa-badge.z1`…`.z5`, same dot-prefixed pill as gym's deficit/mantenimiento/volumen badges) followed by name, use-case text, and the ppm range.

### Macro-Style Detail Cards (`.macros-grid`-adjacent `sec-hdr`/`sec-body`, ported verbatim)
FC máx, FC reposo, and Peso each get their own card: icon square + title + a summary subtitle (latest value + date, mirroring gym's "1.2g prot/kg · 0.5g grasa/kg" sec-sub) + a short history list + a date/value/`.f-btn` add-row. This is where new readings are actually entered; the profile card above is read-only at-a-glance.

### Sesiones Row (kept from the retired estudio build)
Flat row — left color dot (session-type color) + title/sub stack + trailing chevron — opening a bottom sheet with the full detail, rather than gym-tracker's own inline-expanding session card. This is one of the two deliberately-kept estudio-style pieces; don't "fix" it back into a `.hist-session` expand-in-place pattern.

### Sesiones Tab: Hechas / Planificadas (`.metric-row`/`.metric-btn`, ported verbatim)
The second tab (icon unchanged, label "Sesiones") holds two apartados behind a 2-equal-width segmented control: **Hechas** (the sessions-row list above) and **Planificadas** (the week planner). Planificación is not a settings section; it never was meant to live in Ajustes.

### Planificación Week (`.hist-session`/`.hist-hdr`/`.hist-body`, reused)
Each plan week reuses gym-tracker's own collapsible-session component verbatim (tap header to toggle, `›`/`⌄` chevron swap, `.hist-body.open`) — a week behaves exactly like a sessions row, just with editable fields instead of read-only data. Exactly one week is open by default: whichever week contains today, or the next upcoming week if today falls outside the whole plan. Adding a week clones the last week's values and opens the new one for editing.

### Settings Row (`.sett-group`/`.sett-row`/`.sett-icon`, ported verbatim)
Grouped by a small uppercase eyebrow title, one card per group, rows separated by hairlines (never one card per row) — colored icon square + label + optional right-aligned mono state value. Fixed section order: **Datos** → **Preferencias** → **Peligro**, always last and visually separated.

### Buttons
- **Primary (`.cta`/`.save-btn`):** solid white fill, black Bebas Neue uppercase label, `20px` radius, used where no more specific gym-tracker button applies (e.g. "+ Añadir semana", the plain Registrar CTA on rodaje/test days).
- **Segmented control (`.metric-row`/`.metric-btn`):** 2-equal-width buttons, active inverts to white-on-black.
- **Filter pills (`.hist-tabs`/`.hist-tab`):** horizontal-scroll pill row, active inverts to white-on-black — used for the Hechas type filter.

### Cards
Every card in the app shares gym-tracker's real two-layer recipe: a flat base (fill/border/radius/`shadow-card`) plus a later override that swaps the fill for a subtle layered gradient (`160deg, .055→.018→.03`) with `blur(36px) saturate(220%) brightness(1.05)`, and adds a glossy 1px top-edge seam (`::after`, inset 8%). This applies to `.glass`, `.fisico-block`, `.profile-card`, `.sett-group`, `.hist-session`, and `.emom-card` identically — the "almost-invisible depth" the user called out as missing is this exact two-layer background, not a new effect.

## Do's and Don'ts

### Do:
- **Do** keep exactly one `.header` in the whole app — sticky, gym-tracker's real markup/CSS, title "KM TRACKER" never changing per screen; any other title scrolls with its content, per the One-Header Rule.
- **Do** keep each session type's color fixed everywhere it appears — never reassign it to chrome, and never reintroduce per-tab background recoloring.
- **Do** render every logged/derived value in SF Mono, per the Data-Is-Mono Rule.
- **Do** give every Planificación day block the same 4-column grid regardless of how many fields it uses, per the Equal-Grid Rule.
- **Do** treat the nav-indicator's colored glow, the today-hero's shine sweep, and the profile-card's colored `pstat` bars as intentional gym-tracker brand commitments, not defects to flatten.
- **Do** reach for an existing gym-tracker component (and its real class names) before writing anything new — the standing instruction behind every component listed above.

### Don't:
- **Don't** reintroduce Archivo/Archivo Narrow, a shifting background halo, or any other piece of the twice-retired estudio-style (`kit-componentes.html`) skin.
- **Don't** move Planificación back into Ajustes; it is its own apartado (alongside Hechas) inside the Sesiones tab.
- **Don't** give a day block with fewer fields (rodaje) a narrower or re-centered grid — empty placeholder cells keep every block's columns aligned.
- **Don't** convert the Sesiones row back to gym-tracker's own expandable-session pattern, or re-theme the Ajustes "Eliminar" row's red away — those are the two deliberate, named exceptions kept from the retired estudio build. Everything else in the app, including Físico, is gym-tracker's own native pattern now, not an exception.
