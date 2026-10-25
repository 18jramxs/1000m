---
name: 1000 m Tracker
description: Cristal negro profundo con halo de color por sección — tracker de tres sesiones semanales fijas (series/rodaje/velocidad) + test mensual
colors:
  bg-void: "#030304"
  glass-bg: "rgba(255,255,255,.035)"
  glass-bg-hi: "rgba(255,255,255,.07)"
  glass-border: "rgba(255,255,255,.085)"
  c-series: "#2E8BFF"
  c-rodaje: "#22D37A"
  c-velocidad: "#FF9F1C"
  c-test: "#FFD60A"
  c-danger: "#FF3B4E"
  c-neutral: "#8E9BAE"
  c-ajustes: "#6C7A89"
  text-primary: "#FFFFFF"
  text-secondary: "rgba(255,255,255,.60)"
  text-tertiary: "rgba(255,255,255,.34)"
typography:
  hero:
    fontFamily: "Archivo Narrow, Archivo, system-ui, sans-serif"
    fontSize: "clamp(30px,9vw,40px)"
    fontWeight: 700
    lineHeight: 1.02
    letterSpacing: "-.01em"
    fontFeature: "uppercase"
  display-lg:
    fontFamily: "Archivo Narrow, Archivo, system-ui, sans-serif"
    fontSize: "26px-30px"
    fontWeight: 700
    lineHeight: 1
  display-md:
    fontFamily: "Archivo Narrow, Archivo, system-ui, sans-serif"
    fontSize: "16px-22px"
    fontWeight: 700
    lineHeight: 1
  cta:
    fontFamily: "Archivo Narrow, Archivo, system-ui, sans-serif"
    fontSize: "17px"
    fontWeight: 700
    letterSpacing: ".03em"
    fontFeature: "uppercase"
  body:
    fontFamily: "Archivo, system-ui, -apple-system, sans-serif"
    fontSize: "13px-17px"
    fontWeight: 400-600
  caption:
    fontFamily: "Archivo, system-ui, sans-serif"
    fontSize: "8.5px-12.5px"
    fontWeight: 600-800
    letterSpacing: ".03em-.17em"
    fontFeature: "uppercase (most, not all)"
rounded:
  pill: "999px"
  xl: "28px"
  lg: "22px"
  md: "18px"
  sm: "12px"
  icon-tile: "11px"
  tip: "3px-7px"
spacing:
  screen-gap: "22px"
  card-pad: "15px-17px"
components:
  btn-glow:
    backgroundColor: "rgba(255,255,255,.075)"
    border: "1px solid color-mix(in srgb, var(--c) 48%, transparent)"
    boxShadow: "0 0 26px -2px color-mix(in srgb,var(--c) 45%,transparent)"
    rounded: "{rounded.md}"
  glass-card:
    backgroundColor: "{colors.glass-bg}"
    border: "1px solid {colors.glass-border}"
    rounded: "{rounded.lg}"
    backdropFilter: "blur(30px) saturate(118%)"
  tabbar:
    backgroundColor: "rgba(255,255,255,.055)"
    rounded: "{rounded.pill}"
    position: "fixed, floating, bottom"
---

# Design System: 1000 m Tracker

## Overview

**Creative North Star: "The Family Glass, second outfit" — ported verbatim from `kit-componentes.html` (estudio tracker), the sibling app's own component kit, not from gym-tracker.**

As of noviembre 2026 the training model changed completely (three fixed weekly sessions — series de ritmo, rodaje base, velocidad — plus a monthly test replacing velocidad on the first Friday of the month), and the visual system changed with it: this build drops the previous gym-tracker-style skin (Bebas Neue, SF Mono, pill nav with sliding indicator) in favor of estudio-tracker's own language — near-black glass with a top-edge light seam, a single color "halo" radiating from the background that shifts per tab, oversized Archivo Narrow numerals sitting directly on the void rather than inside a card, and a floating pill tab bar. The two apps (`1000m` and `estudio`) are meant to read as the same family now; this is the intentional reskin that establishes it, superseding the earlier "ported from gym-tracker" direction entirely.

The material is near-black glass (`#030304`) everywhere, thinner and less saturated than the previous system (`saturate(118%)` vs. `180%`), with a soft two-point radial halo behind the whole viewport that recolors per tab (blue for Hoy/series, neutral grey for Historial, amber/gold for Progreso, red for Físico, slate for Ajustes). Big numbers — the day's session title, PR tiles, chart deltas, the fisico current-value readouts — use condensed Archivo Narrow directly on the glass or on the bare background; everything administrative (labels, dates, table-like rows) stays small, uppercase, letter-spaced Archivo.

**Key Characteristics:**
- Near-black glass (`.glass`) with a 1px top-edge light seam on every card, no saturated color fill
- A single shifting "halo" background radial-gradient keyed to the active tab/section, not a static accent
- Archivo Narrow condensed bold for headline numerals and short display labels; Archivo for everything else
- Per-session-type color is fixed and carries through the whole app (series blue, rodaje green, velocidad orange, test amber) — never reused for chrome
- Selected/active chip and segmented-control states use the glowing `--c`-tinted `btn-glow` treatment, not a flat invert

## Colors

### Primary — session types (fixed, carried everywhere)
- **Series blue** (`#2E8BFF`): series de ritmo — hero title, CTA glow, notation dot, chart line.
- **Rodaje green** (`#22D37A`): rodaje base — same roles for that type.
- **Velocidad orange** (`#FF9F1C`): velocidad — same roles.
- **Test amber** (`#FFD60A`): test 1.000 — same roles, plus the Progreso tab halo (scoring/achievement association carried over from the retired baremo system, now just "this is the test/achievement color").

### Secondary
- **Danger red** (`#FF3B4E`): Físico tab halo (heart-rate association), delete actions, negative resumen deltas, Z3 warning is amber not red (see Named Rules).
- **Neutral grey** (`#8E9BAE` / `#6C7A89`): Historial and Ajustes tab halos — sections with no single session-type identity of their own.

### Neutral
- **Void** (`#030304`): page background, strictly neutral (no blue tint), per the ported kit's own correction of that defect.
- **Glass** (`rgba(255,255,255,.035)` base / `.07` hi): card fill, always translucent, never opaque.
- **Text primary/secondary/tertiary** (`#fff` / `.60` / `.34`): identical three-step ladder to the ported kit.

### Named Rules
**The Halo-Per-Section Rule.** The background radial-gradient's color (`--halo`) always matches the active tab's assigned color, set on tab click exactly as in `kit-componentes.html`. It is the one "mood" signal on screen; no other chrome element recolors independently of it.
**The Type-Owns-Its-Color Rule.** Each of the four session types (series/rodaje/velocidad/test) keeps one fixed color everywhere it appears — hero title, CTA, agenda dot, history dot, chart line. A color never migrates to a different type or to generic chrome.

## Typography

**Display Font:** Archivo Narrow (ported from `kit-componentes.html`'s `--font-cond`)
**Body/Label Font:** Archivo

This replaces the previous Bebas Neue / SF Mono pairing entirely — intentional, per the reskin's brief. Numbers no longer get a dedicated monospace treatment; `font-variant-numeric: tabular-nums` on the body face does the alignment work instead (again, ported from the kit, which never introduced a mono face).

### Hierarchy
- **Hero** (700, `clamp(30px,9vw,40px)`, uppercase): the day's session-type title on Hoy — the single largest text on any screen.
- **Display lg** (700, 26–30px): fisico current-value readouts, few-point chart deltas.
- **Display md** (700, 16–22px): sheet titles, notation line, PR values, resumen values, the "Descanso" title (a deliberately smaller, non-hero variant of the same display face — see Rest Day under Components) and the few-points arrow/delta chip.
- **CTA label** (700, 17px, uppercase, letter-spacing .03em): the Registrar button only.
- **Body** (400–600, 13–17px): row text, inputs, detail values, plan-editor field values.
- **Caption** (600–800, 8.5–12.5px, mostly uppercase, letter-spacing .03–.17em): every small administrative text — section eyebrows (`.scr-head`/`.label`), chart captions, table/row labels, unit tags (`m`, `/km`, `'`), settings state text, plan-field column headers. One wide step rather than several near-identical ones, since this family of micro-text shares the same job (label something larger) at a continuum of sizes dictated by its immediate container, not by a strict 2–3-step ramp.

## Layout

Single-column mobile stack (`.wrap`, `max-width:460px`), screens toggled via `display:none`/`.active`. Cards flow vertically with a flat `22px` gap (`.wrap` is a `flex-direction:column` with `gap`, not individually-margined cards) — a deliberate simplification versus the old per-card `margin-bottom` approach. Grids are used only for symmetric repeaters: the 3-column PR grid, the 3-column resumen grid. The tab bar is a fixed floating pill, `14px` off the bottom safe area, not a full-width bar; body gets `130px` bottom padding to clear it.

## Elevation & Depth

Flat glass + blur does all the depth work; there is no separate drop-shadow vocabulary (no `shadow-card`/`shadow-card-lg` tier like the retired system). The only shadow-like accents are the `btn-glow` component's colored glow (`box-shadow` built from `color-mix(in srgb, var(--c) …)`) and the tab bar's ambient drop shadow.

### Named Rules
**The Top-Edge Seam Rule.** Every `.glass` card and `.btn-glow` element carries a 1px `::before` gradient seam (transparent → `rgba(255,255,255,.3)` → transparent) across its very top edge — the one universal signature ported from the kit. Apply it to any new glass-like surface.

## Shapes

Four radius steps, all larger than the retired system's: `12px` (inputs, small chips), `18px` (buttons, icon tiles), `22px` (default cards), `28px` (the bottom sheet's top corners), plus a `999px` pill for the tab bar and segmented controls. Borders are always 1px hairlines at `.085` opacity. The settings-row icon square uses `11px` (`icon-tile`) rather than `12px` — a verbatim port of gym-tracker's own icon-tile radius, kept as its own token for cross-app consistency rather than snapped to the nearest step. A `3px`–`7px` "tip" range is used only for small decorative details sized relative to their own element's height, never a card/button shape: the tapered bottom corners of a bar-chart bar (`7px 7px 3px 3px`), the caída-de-series progress-pill track/fill (`5px`, half its own `10px` height), the small time-chip in "Última vez" (`7px`), and the bottom-sheet's drag handle (`3px` on a `36×5px` bar). These are fixed micro-details ported from or matched to `kit-componentes.html`'s own equivalents — not meant to join the card-radius scale.

## Components

### Buttons
- **Primary (`btn-glow`):** `--c`-tinted translucent fill + colored glow shadow + top-edge seam; used for the Registrar CTA, the active segmented-control button, and the Ajustes "Añadir semana" action. The glow color is whatever session-type/halo color is contextually active — there is no separate fixed "CTA blue" like the retired system had.
- **Secondary (`btn-ghost`):** flat `rgba(255,255,255,.035)` fill, hairline border, no glow — used for "Eliminar semana" and similar low-emphasis actions.

### Segmented Control (`.seg`)
Pill-shaped row of equal-width buttons; the active button gets the full `btn-glow` treatment keyed to `--halo`. Used for Historial's type filter and nowhere else that used to be a "filter-chip" row in the retired system.

### Cards (`.glass`)
Translucent flat fill (`rgba(255,255,255,.035)`), 1px hairline border, top-edge seam, `22px` radius. No gradient-layered fill and no drop shadow — simpler than the retired `.fisico-card` recipe by design (ported from the kit as-is).

### Bottom Sheet (`.sheet`)
Slides up from the bottom, `28px` top corners only, drag-handle bar, used for all data entry (registro) and record detail — the one modal pattern in the app.

### Tab Bar (`.tabbar`)
Floating pill, 5 icon-only buttons (Hoy / Historial / Progreso / Físico / Ajustes), active button gets a `--halo`-tinted gradient fill + glow, matching the kit's tab bar exactly. Icons are stroke SVGs only — no emoji anywhere in the app, including the info/pitidos affordance, which is a stroke "info" glyph.

### Adaptive Charts
Hand-rolled inline SVG (no Chart.js, no external chart library) — a deliberate departure from the retired system, matching the kit's own hand-SVG curve/bar components. Charts with ≤2 data points render as two big juxtaposed numbers with a delta chip instead of a line, since a line through two points communicates nothing; 3–5 points get a labeled line; >5 points label only the first, last, and best point. An empty chart (no qualifying sessions yet) never renders the heavy centered `.empty` placeholder — it collapses to `.empty-mini`, a single left-aligned sentence naming the specific session that will make it appear ("Aparece con tu primera sesión de series"), sized to its own text with no reserved filler height.

### Screen Header (`.scr-head`)
Every screen's eyebrow title — the plain `h2.sec` on Historial/Progreso/Físico/Ajustes, and the date line on Hoy — is wrapped in `.scr-head`: `position:sticky; top:env(safe-area-inset-top,0px)`, solid `var(--bg)` fill, above a fixed `body::after` strip of the same color that masks the exact status-bar height. Together these guarantee no screen title can ever render under the iOS status bar's clock/battery, on first paint or after scrolling — this is a correctness mechanism, not a decorative one, and any new screen must get the same wrapper.

### Rest Day (Hoy, no session today)
A deliberately low-key state, not a second hero: the date eyebrow stays in `.scr-head`, "Descanso" renders at **Display md** size (`.hoy-tipo-sm`, 22px) rather than the session hero's `clamp(30–40px)`, followed immediately by a "Próximo entreno" card (full date + type + compact notation of the next non-rest day) and an "Esta semana" card reusing the exact `.agenda-day` row recipe (dot + label + Hecho/Sin registrar/HOY status) for the week's three fixed sessions, then the same collapsed Agenda as any other day.

### Settings Row (Ajustes)
Ported from gym-tracker's settings pattern: screens are a sequence of `.settings-group` (small uppercase `.settings-group-title` eyebrow above one `.glass` card), each card holding `.settings-row`s separated by hairline top-borders (not one card per row) — icon square (`.settings-icon`, `icon-tile` radius, tinted per row) + label (flex) + optional right-aligned `.state` value. Sections in fixed order: **Plan** (the week editor) → **Datos** (export/import) → **Preferencias** (the ritmo/tiempo display toggle) → **Peligro** (reset, red icon+text, always last and visually separated into its own group). A small, heavily dimmed app-name/author/version footer closes the screen.

## Do's and Don'ts

### Do:
- **Do** keep each session type's color fixed everywhere it appears (hero, CTA, dots, charts) — never reassign it to chrome.
- **Do** let the background halo recolor per active tab, per the Halo-Per-Section Rule.
- **Do** use stroke SVG icons exclusively; the app has a hard no-emoji rule end to end, including the agenda toggle and the pitidos info affordance.
- **Do** render small numeric values with `font-variant-numeric:tabular-nums` on Archivo rather than introducing a mono face.
- **Do** fall back to the two-number/delta treatment for any chart with ≤2 points rather than drawing a misleadingly sparse line.
- **Do** wrap every screen's title in `.scr-head` and shrink every data-less chart to `.empty-mini` with a specific, actionable sentence — these are the two standing layout-correctness rules, not one-off fixes.

### Don't:
- **Don't** reintroduce Bebas Neue or an SF-Mono-style data face — this build retired that pairing in favor of Archivo/Archivo Narrow across the board.
- **Don't** add a drop-shadow tier to ordinary `.glass` cards; depth here comes from translucency + blur + the top-edge seam only, not shadows.
- **Don't** pull in Chart.js or any charting dependency; all graphs are hand-rolled inline SVG, consistent with the kit's own hand-SVG components.
- **Don't** give the tab bar's active state a second accent color independent of `--halo` — the active tab button's glow must always read as the same color currently driving the page's background halo.
- **Don't** render a generic "Sin datos todavía" placeholder at full card height for a scoped chart — it must name what specifically will fill it, at minimal height, per the Adaptive Charts empty-state behavior.
- **Don't** make "Descanso" the visual protagonist of the Hoy screen — it renders at Display md, not Hero, and is immediately followed by the next real training day.
