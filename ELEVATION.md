# Homepage elevation plan — toward Legora / Harvey / Happy Robot

What separates those three sites from ours today, verified against their live markup, and the section-by-section plan to close the gap.

## What they actually do

**Harvey** (ink `#1E1D1A` on warm eggshell): a hero **video loop**, editorial photography and product UI in rounded frames with a gentle hover scale, a hard-numbers stats row (65+ countries, 1,500+ customers, 142,000+ users), serif display type, dark band moments for rhythm.

**Legora** (our palette source): product screenshots in framed panels on `#E6E6E6` fields, emerald `#005032` carrying CTAs and full sections, customer logos plus stat numbers, big serif statements.

**Happy Robot** (bone `#f3f1e6` + near-black `#0E0D0C`): full-bleed **hero video**, a giant wall of real recognizable logos (DHL, Uber, Ryder, CMA CGM), narrative scroll storytelling ("It starts with agents → Agents need context → Deployed in the wild"), case-study cards anchored on one hard metric ("78% autonomous execution"), alternating light/dark sections.

## The shared playbook

1. **Real media, never empty boxes.** The hero shows the product or a cinematic loop. This is the single biggest gap on our page today.
2. **Product UI lives in styled frames** — rounded, hairline-bordered, sitting on a tinted panel, often with slight parallax or hover scale.
3. **Numbers as proof.** A stats row of 3–4 hard metrics directly after the logos.
4. **Rhythm through drenched sections.** At least one full-bleed dark or brand-color section mid-page, not just at the end.
5. **One testimonial as an editorial moment** — oversized serif quote, headshot, firm name — instead of a quote grid.
6. **Choreographed motion**: staggered hero load, scroll reveals, parallax on media. Always subtle, always reduced-motion-safe.
7. **A branded footer moment** — the wordmark huge, almost a sign-off.

## Section-by-section plan

1. **Hero** — keep headline and copy. Replace the gray 16:9 box with a product screenshot inside a "browser frame" (rounded 12px, hairline border, top bar with three dots) sitting on a full-width `--field` panel that bleeds off the bottom of the fold. Subtle parallax float on scroll. Slot for an ambient video loop later.
2. **Logo strip** — swap gray boxes for real monochrome logos at 28–32px height, slightly larger than typical (Happy Robot scale). Litera line stays.
3. **NEW: stats band** — directly after logos: three oversized serif numbers with one-line labels. Candidates from existing site copy (confirm real values before launch): "4.2 weeks — signal detected before the RFP", "1,000+ — signals surfaced per week", "AmLaw 200 — firms served". This is the Legora/Harvey proof move we currently lack.
4. **Problem trio + statement** — keep as is; they already follow the editorial playbook.
5. **Products** — each screenshot gets the same framed treatment as the hero on a `--field` panel. Make the middle row (ERM) a **full-bleed ink-dark section** (`#0D1016` bg, paper text, emerald accents) for mid-page rhythm — the Happy Robot alternation. Add a quiet hover scale (1.02) on frames.
6. **Shift table** — keep, but tighten vertical padding; it reads slightly long against the new rhythm.
7. **Proof** — promote the Jeffrey Merk quote to a full-width editorial moment: largest serif on the page, headshot left, name and firm under it. The two remaining quotes sit smaller in a row beneath. Pull-quote stays as the section opener.
8. **Closing band** — keep the emerald drench; add the wordmark oversized and cropped at the band's bottom edge as a watermark (footer-moment device).
9. **Motion pass** — keep current reveals; add hero load choreography (label → headline lines → copy → CTAs → frame, 80ms stagger), parallax (±12px) on framed media, ease-out-quint everywhere, all inside `prefers-reduced-motion: no-preference`.
10. **Type scale push** — hero display up to `clamp(3rem, 6vw, 5.25rem)`; stats numbers in serif at similar scale; everything else unchanged.

## Asset manifest (drop into `assets/` on main)

The page ships with gray placeholders at these exact paths and aspect ratios; committing a file at the path makes it appear, no code change needed.

| Path | Size | Content |
|---|---|---|
| `assets/hero-product.png` | 2880×1620 | Signals dashboard, light UI, clean demo data |
| `assets/hero-loop.mp4` (optional) | ≤8 MB, 16:9 | Ambient product/brand loop, no audio |
| `assets/product-signals.png` | 1600×1200 | Signals feed detail |
| `assets/product-erm.png` | 1600×1200 | Relationship coverage view (will sit on dark — light UI reads best) |
| `assets/product-cleanse.png` | 1600×1200 | Data hygiene view |
| `assets/logos/holland-knight.svg` … `white-case.svg`, `dentons.svg`, `levenfeld.svg`, `caravel.svg`, `carahsoft.svg` | mono, ink `#0D1016` | One-color logo versions |
| `assets/headshots/merk.jpg`, `baylis.jpg`, `rubin.jpg` | 480×480 | Testimonial headshots |

## Verification

Local preview at 1440 and 375 widths after each section lands; check placeholder fallback by loading with an empty `assets/`; confirm reduced-motion disables parallax and choreography; Lighthouse pass on the deployed Vercel URL once shipped.
