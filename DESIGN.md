# DESIGN.md — Postilize

## Theme
Light. Scene: a managing partner reviewing vendors on a laptop in a daylit corner office; the page should read like printed firm stationery, not software.

## Logo
The real Postilize wordmark SVG (from the live site CDN, white original at assets-logo.svg) is inlined with fill="currentColor" so it takes ink on light grounds. Never substitute a text wordmark.

## Color
Strategy: crisp near-white/ink ground with one committed deep emerald that fully owns CTAs and the closing band. Reference: Legora (#005032 emerald on #FAFAF9/#E6E6E6 cool neutrals, #0D1016 ink).

- --paper: #FAFAF9 (page ground, near-white)
- --ink: #0D1016 (headlines, body on paper; cool blue cast)
- --ink-soft: #6B6B6B (secondary text, captions)
- --hairline: #E4E4E2 (borders, rules)
- --field: #E9E9E7 (placeholder boxes, quiet panels)
- --green: #005032 (CTAs, links, closing band; the Legora-register emerald)
- --green-deep: #003D26 (closing band gradient floor / hover)
- --paper-on-green: #FAFAF9 (text on green)

Never #000 or #fff. No other hues.

## Typography
- Display: Source Serif 4 (opsz), weights 300–400. Tight tracking (-0.015em to -0.025em), line-height 1.04–1.12 on display sizes.
- Body/UI: Hanken Grotesk, weights 400/500/600. 17px body, line-height 1.6.
- Labels: Hanken Grotesk 600, 11–12px, uppercase, +0.12em tracking, ink-soft.
- Scale ratio ≥1.25. H1 clamp(2.75rem, 5.5vw, 4.5rem).
- Body measure ≤ 65ch.

## Layout
- Max content width 1120px, 24px gutters mobile / 48px desktop.
- Section rhythm: clamp(6rem, 10vw, 10rem) vertical. Vary: trust strip and statement sections tighter.
- Left-aligned single grid throughout. Centered only: big statement, final CTA band.
- No nested cards, no side-stripe borders, no icon-card grids.

## Components
- Buttons: 1px radius 999px pill or small radius? → small radius (6px), 14px/600 sans, green fill with paper text (primary); ghost with hairline border (secondary).
- Placeholders: --field fill, 1px --hairline border, 6px radius, small centered uppercase label in ink-soft naming the asset.
- Rules: 1px --hairline, used sparingly to structure, never decorative stacks.

## Motion
One subtle page-load fade-and-rise on hero elements (staggered, ease-out-quint, ≤600ms). Optional quiet scroll-reveal on sections (opacity + 12px rise). Nothing else.
