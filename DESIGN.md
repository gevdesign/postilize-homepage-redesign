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

### Verified benchmark data (pulled from competitor live CSS, June 2026)
- Harvey: fonts custom HarveySerif + ABC Diatype Variable; ivory #FAFAF9 (gray-50-ivory), ink #0F0E0D (gray-950-ink), gray-200 #E5E5E3, gray-600 #706D66; muted accents alabaster #DBD9D1, blush #D9CDCC, casal #333F40, bronze #593D3A; hero video loop; framed imagery with hover scale 1.02.
- Legora: fonts Rhymes Display Light + Domaine Display Narrow (display), Suisse Intl Book/Medium (body); emerald #005032 dominant, ink #0D1016, off-white #FAFAF9, panel #E6E6E6, hover green #003D26.
- Our --paper matches both sites' off-white exactly; hairline and ink-soft sit within 1–2 points of Harvey's grays.

## Typography
- Display: Source Serif 4 (opsz), weights 300–400. Tight tracking (-0.03em on display, -0.015em elsewhere), line-height 1.04–1.12 on display sizes.
- Body/UI: Geist, weights 400/500/600. 15px body, line-height 1.6; component text runs 13–14px (.82–.9rem). Legora's measured system runs 13–14px body. (Geist chosen as the closest free analog to the competitors' Suisse Intl / ABC Diatype; replaced Hanken Grotesk, which read too warm/humanist for the register.)
- Scale contrast is the premium signal (measured on legora.com): body 14px vs stat numerals ~110px vs H1 60px. Ours: 15px body, display clamp to 76px, stat numerals clamp to 104px — the largest type on the page is the stats, not the hero.
- Stats render as Legora-style ruled rows: hairline top, giant serif numeral left, 12–13px gray label in a right column. Never columns of equal cards.
- Buttons are pills (border-radius 999px), 13–14px/600 text — measured from Legora (99px radius).
- Rejected: Gloock as display serif (tested side by side; too heavy/fashion-editorial against Harvey's and Legora's light serifs).
- Labels: Hanken Grotesk 600, 11–12px, uppercase, +0.12em tracking, ink-soft.
- Scale ratio ≥1.25. H1 clamp(2.75rem, 5.5vw, 4.5rem).
- Body measure ≤ 65ch.

## Full-bleed system (siteinspire research, June 2026)
Benchmarks: Quinn Global Tax Law (quinngtl.com) and Old Tom Capital (oldtomcapital.com), both by Highly Necessary; plus Legora/Happy Robot heroes. The anti-pattern ("AI slop"): centered hero text above a contained rounded image, one repeated section-grid, single background color throughout.

- Hero: 100svh full-bleed photography, nav and headline OVERLAID on the image (transparent header that turns solid past the hero), gradient scrim for legibility, film-grain overlay.
- Section rhythm by background shifts: photo -> ink -> paper -> emerald drench -> field -> ink+photo split -> paper -> photo band -> emerald. Never two adjacent sections on the same ground.
- Asymmetric splits: media runs flush to the viewport edge (no border-radius), copy in a measured column on the other side (Quinn).
- Sticky editorial column beside scrolling giant two-tone stat rows (Old Tom): first line ink, second line emerald, both at display scale.
- Ghosted oversized serif numerals (No. 1/2/3) as product section markers.
- Full-bleed photo quote band with the testimonial overlaid (Legora ROI-band pattern).
- Film grain: SVG feTurbulence overlay at ~10% on photo sections; photos graded slightly desaturated.

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
