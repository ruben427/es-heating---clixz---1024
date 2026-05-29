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
