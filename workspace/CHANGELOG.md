<instructions>
## 🚨 MANDATORY: CHANGELOG TRACKING 🚨

You MUST maintain this file to track your work across messages. This is NON-NEGOTIABLE.

---

## INSTRUCTIONS

- **MAX 5 lines** per entry - be concise but informative
- **Include file paths** of key files modified or discovered
- **Note patterns/conventions** found in the codebase
- **Sort entries by date** in DESCENDING order (most recent first)
- If this file gets corrupted, messy, or unsorted -> re-create it. 
- CRITICAL: Updating this file at the END of EVERY response is MANDATORY.
- CRITICAL: Keep this file under 300 lines. You are allowed to summarize, change the format, delete entries, etc., in order to keep it under the limit.

</instructions>

<changelog>
## 2026-06-02
- Renamed class `SVG-phone-icon` → `chevron-bullit` in all files
- Affected: `index.html` (3×), `offerte.html` (3×), `index-standalone.html` (3× HTML + 1× CSS), `style.css` (1×), `offerte.css` (1×)

## 2026-06-01 (session 4)
- Desktop `.img` (index) en `.hero-banner` (offerte): `width: 100%`, geen margin/padding — volledige breedte, geen downscale
- Mobile `.img` + `.hero-banner`: `width: calc(100% - 32px)`, `margin: 0 16px` — alleen breakpoint <768px krijgt 16px padding

## 2026-06-01 (session 3)
- `.img` (movie header) op desktop: `width: calc(100% - 32px)`, `margin: 0 16px`, `max-width: none` — geen downscale, geen max-width, alleen 16px padding links/rechts
- Mobile `.img` ook bijgewerkt: fixed 768px verwijderd, nu ook `calc(100% - 32px)` + `margin: 0 16px`

## 2026-06-01 (session 2)
- Offerte mobile (<768px): `col-main` en `col-sidebar` beide `width: 100%`

## 2026-06-01
- Alle `border-radius: 48px` → `32px` in `style.css`, `offerte.css` (sidebar, download-card)
- Alle `font-size: 18px` → `16px` met `line-height: 24px` in `style.css`, `components/tile.css`, `offerte.css`
- Offerte content-inner kolommen: `col-main` → `flex: 0 0 60%`, `col-sidebar` → `flex: 0 0 calc(40% - 48px)`

## 2026-05-31 (session 16)
- Alle tile-gerelateerde CSS (`.tile`, `.tile-2`, `.layer-wrapper`, `.tiles-wrapper`, `.tiles-grid`, `.tiles`, `.tiles-feedback`, badge/button/content classes) verplaatst van `style.css` naar `components/tile.css`
- Bijbehorende desktop + mobile media-query blokken ook verwijderd uit `style.css`
- `style.css` bevat nu alleen nog niet-tile pagina-stijlen

## 2026-05-31 (session 15)
- `tile-table` tbody/tr/td gezet op `display:block; width:100%` zodat `.tile` de volledige kolombreedte pakt
- `table-layout:fixed` toegevoegd aan `.tile-table` om col-width te forceren
- Geen max-width op desktop — mobile behoudt bestaande `width:100%` via media query

## 2026-05-31 (session 14)
- Tiles en feedback-widget volledig losgekoppeld in `index.html`: tiles zitten nu in eigen `<div class="tiles">`, feedback in eigen `<div class="tiles-feedback">`
- `.tiles-grid` in `style.css` omgezet van `display:grid` naar `display:flex; flex-direction:row; align-items:flex-start`
- `.tiles` is nu `flex:1` met interne `grid-template-columns:1fr 1fr` — los van feedback
- `.tiles-feedback` is `flex:0 0 194px; align-self:flex-start` — altijd top-aligned
- Mobile: `tiles-grid` wordt `flex-direction:column`, `tiles-feedback` krijgt `width:100%`

## 2026-05-31 (session 13)
- `.tile` divs gegroepeerd in één `<div class="tiles">` wrapper in `index.html`
- `.tiles-grid` terug naar `1fr 194px` (tiles links, feedback rechts)
- `.tiles` krijgt `grid-template-columns: 1fr 1fr` — 2 tiles per rij binnen de wrapper
- Mobile: `.tiles` ook naar `1fr` zodat tiles verticaal stapelen

## 2026-05-31 (session 12)
- `tile-table` wrapper volledig verwijderd uit `index.html` en `components/tile.html`
- `.tile` divs zijn nu directe grid-children van `.tiles-grid` — 2 tiles per rij via `grid-template-columns: 1fr 1fr 194px`
- `.tile-table` CSS regels verwijderd uit `components/tile.css`

## 2026-05-31 (session 11)
- `<table class="tile-table">` in `index.html` vervangen door `<div class="tile-table">` — geen table markup meer nodig in index
- `tile.html` behoudt nog steeds de `<table>` wrapper voor het externe injectiesysteem

## 2026-05-31 (session 10)
- Verplaatst `.tile-table` CSS van `style.css` naar `components/tile.css`
- `tile.html` heeft nu nog maar 1 `<link>` tag (alleen `tile.css`) — `style.css` link verwijderd
- `.tile-table tr/tbody/td { display:contents }` nu ook in `tile.css` aanwezig (zonder `.element` scope)

## 2026-05-31 (session 9)
- Each injected tile now has its OWN `<table class="tile-table">` wrapper in `index.html`
- `tile.html` stripped to bare minimum: only 2 `<link>` tags + `<table><tr><td><div class="tile">` — no head/html/style
- `tiles-grid` CSS changed to `1fr 1fr 194px` so two tile columns flow naturally, feedback stays col-3
- `.tile-table tr/tbody/td` all `display:contents` so `.tile` divs are direct grid children
- Removed old single shared `<table class="tiles">` and all related `.tiles tr/td` grid rules

## 2026-05-31 (session 8)
- Fixed injection structure: `<table><tr><td>` now fixed in `index.html` as permanent wrapper
- START/END markers now sit INSIDE the `<td>`, system injects only `.tile` divs between them
- `<td>` styled as `display:grid; grid-template-columns:1fr 1fr` → tiles flow 2-per-row
- Updated `style.css`: `.tiles tr { display:contents }`, `.tiles td { display:grid }`
- Updated `components/tile.html` to match same structure (table>tr>td>markers>tile)

## 2026-05-31 (session 7)
- Fixed `index.html`: elke `.tile` nu in eigen `<tr><td>` i.p.v. twee tiles in één `<td>`
- Feedback widget blijft buiten de `<table>`, in `.tiles-feedback`
- START/END markers zitten rondom alle `<tr>` rijen binnen de `<table>`

## 2026-05-31 (session 6)
- Corrected table/marker structure in `index.html`, `index-standalone.html`, `components/tile.html`
- `<table>` now lives OUTSIDE the START/END markers; markers sit INSIDE `<table>` so system injects `<tr><td>tile</td></tr>` rows between them
- `tile.html` now shows one `<tr><td><div class="tile">` as the repeating component example

## 2026-05-31 (session 5)
- Merged all separate `<table>` wrappers into ONE shared `<table>` in `components/tile.html`, `index.html`, `index-standalone.html`
- Each tile is now a `<tr><td>` row inside one table — required so external system can inject regel-code rows

## 2026-05-31 (session 4)
- Wrapped every `.tile` div in `<table><tr><td>` in `components/tile.html`, `index.html`, `index-standalone.html`
- Required by external templating system to inject regel-code between tiles

## 2026-05-31 (session 3)
- Replaced all `#QH.Offerte regel landingspagina#` markers with `<!-- START/END: Offerte regel landingspagina -->` in `components/tile.html`, `index.html`, `index-standalone.html`
- Reason: `#` character conflicts with user&#39;s external templating system

## 2026-05-31 (session 2)
- Created `components/tile.css` — extracted all inline `<style>` from `components/tile.html`
- `tile.html` `<head>` now has a single `<link rel="stylesheet" href="tile.css" />` instead of inline styles

## 2026-05-31
- Removed `<table><tr><td>` wrapper from inside `.tiles` in `index.html`
- `.tile` divs are now direct children of `.tiles` so CSS grid picks them up correctly

## 2026-05-29 (session 6)
- Applied grid layout to `index.html` + `style.css` (was still using old `display:flex` on `.tiles`)
- Added `tiles-grid`, `tiles`, `tiles-feedback` HTML structure to `index.html`
- Updated `style.css`: `.tiles-grid` = `1fr 194px`, `.tiles` = `1fr 1fr` sub-grid, `.tiles-feedback` pinned col-2 row-1
- Removed old `flex: 1` / `align-self: stretch` from `.tile` and `.tile-2` in `style.css`
- Mobile: grids collapse to single column, feedback drops below tiles

## 2026-05-29 (session 5)
- Replaced `<table>` layout with CSS grid in both `components/tile.html` and `index-standalone.html`
- Outer grid: `tiles-grid` = `1fr 194px` (offerte tiles left, feedback widget always right)
- Inner `tiles` sub-grid: `1fr 1fr` so offerte tiles flow 2-per-row, wrapping naturally
- Feedback widget pinned `grid-column: 2 / grid-row: 1`, always top-right regardless of tile count
- Mobile: both grids collapse to single column, feedback drops below tiles

## 2026-05-29 (session 4)
- Wrapped tile in `<table>` layout in `components/tile.html` with `#QH.Offerte regel landingspagina#` marker
- Added `#QH.Offerte regel landingspagina#` open/close comment markers around offerte tiles in `index-standalone.html`
- Markers wrap only the offerte `.tile` cards (not the feedback widget) for dynamic injection

## 2026-05-29 (session 3)
- Created `styleguide-page.html` — fully self-contained HTML+CSS styleguide
- Uses Google Fonts Lato import and all three brand CSS variables in inline `<style>` tag
- Covers: color swatches, typography scale, buttons, badges, cards, form elements, alerts

## 2026-05-29 (session 2)
- Added CSS custom properties `--color-primary`, `--color-secondary`, `--color-cta` to `:root` in `globals.css`
- Replaced all hardcoded `#008080` / `#B80153` / `#dd006d` color values in `style.css` with variables
- Updated Google Fonts import to Lato-only (ital,wght variants); removed Outfit and Nunito imports
- Replaced all non-Lato `font-family` declarations in `style.css` and `components/feedback-widget.css`
- Resolved leftover `var(--core-color-*)` / `var(--headline-*)` / `var(--text-copy-*)` token references

## 2026-05-29
- Replaced restricted font `Axiforma-Bold` with `Nunito:wght@700` (closest Google Font: geometric rounded sans, bold weight)
- Removed `@FONTWARNING` comment and `@font-face` declaration from `globals.css`
- Updated Google Fonts import to use CSS2 API with all weights for Lato, Outfit, Nunito
- Updated `style.css` `.text-wrapper-8` font-family from `"Axiforma-Bold"` to `"Nunito"`
</changelog>
