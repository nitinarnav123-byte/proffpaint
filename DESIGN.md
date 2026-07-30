---
name: ProffPaint AS
description: An editorial, catalog-style clay-and-gold identity for a full-service Oslo/Viken painter, built around a literal colour-index motif.
colors:
  clay-paper: "#f6f1ea"
  clay-paper-deep: "#ece2d4"
  ink: "#221f1c"
  ink-warm: "#2f2a25"
  mid-clay: "#6b5f54"
  faint-clay: "#8a7d6e"
  gold: "#b5703a"
  gold-light: "#d99a5f"
typography:
  display:
    fontFamily: "Cormorant, Georgia, serif"
    fontSize: "clamp(4.5rem, 12vw, 11rem)"
    fontWeight: 300
    lineHeight: 0.88
    letterSpacing: "-0.03em"
  headline:
    fontFamily: "Cormorant, Georgia, serif"
    fontSize: "clamp(2.6rem, 7vw, 6.5rem)"
    fontWeight: 300
    lineHeight: 0.9
    letterSpacing: "-0.02em"
    fontVariation: "italic"
  body:
    fontFamily: "DM Mono, Courier New, monospace"
    fontSize: "0.9rem"
    fontWeight: 300
    lineHeight: 1.9
    letterSpacing: "normal"
  label:
    fontFamily: "DM Mono, Courier New, monospace"
    fontSize: "0.72rem"
    fontWeight: 400
    lineHeight: 1.4
    letterSpacing: "0.18em"
rounded:
  all: "0px"
spacing:
  section-sm: "clamp(3rem, 6vw, 6rem)"
  section-lg: "clamp(5rem, 10vw, 10rem)"
  gap-hairline: "2px"
components:
  button-primary:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.clay-paper}"
    rounded: "{rounded.all}"
    padding: "0.95rem 2.1rem"
  button-primary-hover:
    backgroundColor: "{colors.gold}"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.mid-clay}"
    rounded: "{rounded.all}"
    padding: "0.95rem 2.1rem"
---

# Design System: ProffPaint AS

## Overview

**Creative North Star: "The Colour Index"**

The system reads as a painter's own colour-reference archive, not a marketing site pretending to be a design studio. Every recurring motif ties back to how a paint professional actually catalogs their work: a literal paint-swatch strip divides sections, gallery images are captioned with roman numerals like plates in a specimen book, process steps and timeline entries are indexed by number, and body copy runs in a monospace typeface, the register of a spec sheet or inventory log, not a sales pitch. Cormorant's light italic serif carries the one voice that is emotional and human: headlines, pull-quotes, testimonials. Everything else stays precise, quiet, cataloged.

This produces a genuinely unusual register for a Norwegian håndverker site: gallery/atelier rather than tradesman-template. The warm clay backgrounds and gold accent read as pigment and material, reinforcing the trade without resorting to paint-roller iconography.

**Key Characteristics:**
- DM Mono carries all body and label text — a deliberate, unusual choice that makes the whole site feel measured and cataloged rather than "designed"
- Cormorant italic serif is reserved for the single emotional register: headlines, pull-quotes, testimonials, numbered indices
- Warm clay/paper backgrounds with a single gold accent, never more than a thin rule, label, or button
- Zero border-radius anywhere — every edge is square, reinforcing the archival/index feel
- Sparse hairline rules (1px) do the structural work that cards and shadows would do elsewhere

## Colors

Drawn directly from the trade's own material: paint pigment and raw canvas/paper.

### Primary
- **Warm Ink** (`#221f1c`): dominant text and dark-surface color. Body ink, primary button fill, dark statement/CTA sections.

### Secondary
- **Burnished Gold Pigment** (`#b5703a`): the accent, rationed to labels, rules, hover states, and the gold-filled CTA button inside dark sections. Never a fill or a large surface.
- **Gold Pigment, Light** (`#d99a5f`): hover state for gold elements only.

### Neutral
- **Clay Paper** (`#f6f1ea`): the primary page background.
- **Clay Paper, Deep** (`#ece2d4`): the secondary/alternating background and image placeholder fill, used via the `.sec-tint` section variant.
- **Mid Clay** (`#6b5f54`): secondary text, body copy, descriptions.
- **Faint Clay** (`#8a7d6e`): tertiary text — labels, captions, counts.

### Named Rules
**The Rationed Gold Rule.** Gold marks something (a label, a rule, an active accent, a button) and never fills a surface. The system has exactly one accent color; it stays rare by construction.

**The Section-Tint Rule.** Section backgrounds shift via CSS custom-property overrides on three named variants — `sec-tint` (warm neutral), `sec-clay` (deeper clay, gold shifts darker for contrast), `sec-dark` (near-black ink, all neutrals invert) — rather than one-off hex values per section. Any new section reuses one of these three, it doesn't invent a fourth.

## Typography

**Display Font:** Cormorant (with Georgia, serif fallback) — light weight, used italic for headline registers.
**Body Font:** DM Mono (with Courier New, monospace fallback).

**Character:** An unusual, deliberate pairing: a light, elegant italic serif for emotional moments against a monospace body that gives everything else the precision of a specimen label. The contrast between "handwritten signature" and "measured catalog entry" is the entire typographic idea.

### Hierarchy
- **Display** (300 weight, `clamp(4.5rem, 12vw, 11rem)`, line-height 0.88, letter-spacing -0.03em): the hero business-name treatment only.
- **Headline** (300 weight italic, `clamp(2.6rem, 7vw, 6.5rem)`, line-height 0.9): section/page titles (Prosjekter, Tjenester, Galleri, etc).
- **Title** (300–400 weight, ~1.3–3.2rem, often italic): card and component headings (service names, process step titles, value cards).
- **Body** (300 weight, 0.9rem, line-height 1.9): paragraph copy. Consistently loose line-height across the whole site — the mono type needs the extra breathing room to stay readable at small sizes.
- **Label** (400 weight, 0.66–0.72rem, letter-spacing 0.18–0.22em, uppercase): eyebrows, section indices, form labels, footer headings — always mono, always gold when it's the primary accent label.

### Named Rules
**The One-Voice Italic Rule.** Cormorant italic is reserved for moments that should feel human: headlines, testimonial quotes, numbered milestones. It never appears in body copy, labels, or UI chrome — those stay in DM Mono.

## Layout

No `max-width` container constrains most sections — they run edge to edge with internal `clamp()` padding, giving the site a poster/gallery-wall feel rather than a centered-document feel. The signature work-grid uses an asymmetric masonry layout (`3fr 5fr 3fr` columns, uneven row spans) rather than a uniform grid, so the gallery reads as curated rather than templated.

Section rhythm is generous and fluid (`clamp(3rem,6vw,6rem)` for standard sections, `clamp(5rem,10vw,10rem)` for the most prominent bands) with hairline 1px rules doing the separating work between sections, rather than background-color changes alone.

## Elevation & Depth

Flat, with zero shadows anywhere in the system. Depth and separation come entirely from hairline 1px rules (`--rule`) and background-tint shifts between the three section variants, plus a subtle repeating diagonal-line texture (`repeating-linear-gradient`) on dark sections. This is a deliberate "no shadows" system — hover states use image `transform:scale()`, text color shifts, and reveal opacity, never a box-shadow.

### Named Rules
**The No-Shadow Rule.** This system conveys depth through rules, tint, and texture, never `box-shadow`. Adding a shadow anywhere breaks the flat, paper-like material logic.

## Shapes

Zero border-radius anywhere in the system (`rounded.all: 0px`) — every button, card, input, and image container is perfectly square. This is what makes the "index/catalog" metaphor read as intentional rather than accidental; a rounded corner anywhere would read as a different, softer brand.

## Components

### Buttons
- **Shape:** perfectly square, no radius.
- **Primary (`.btn-p`):** ink fill, clay-paper text, `.95rem 2.1rem` padding, `52px` minimum height, uppercase mono label with wide tracking. Shifts to gold fill on hover with a `translateY(-1px)` lift. Inside dark CTA bands, the primary button is gold-filled by default (inverted for contrast).
- **Ghost (`.btn-o`):** transparent fill, 1px ink-at-20%-opacity border, mid-clay text. On dark/photo backgrounds, switches to a white-at-40%-opacity border variant (`.on-dark`).

### Cards / Containers
- **Corner Style:** square, no exceptions.
- **Background:** clay-paper or clay-paper-deep depending on section variant.
- **Shadow Strategy:** none — see The No-Shadow Rule.
- **Border:** 1px hairline rules only, never a full card border unless it's a genuine grid divider (booking cards, value cells).

### Inputs / Fields
- **Style:** near-transparent ink-tinted background (`rgba(34,31,28,.03)`), 1px top/side border plus a slightly heavier bottom border, square corners, `48px` minimum height.
- **Focus:** border shifts to gold, background tints slightly gold.
- **Error:** border and inline error text shift to a dedicated warm red (`#a04030`).

### Navigation
- **Style:** fixed, transparent at rest, gains a blurred paper background and border-bottom rule once scrolled. Center-aligned nav links in uppercase mono, gold on hover/active. Mobile collapses to a two-line hamburger opening a full-screen menu with oversized italic Cormorant links.
- **Signature element:** the roman-numeral gallery captions (I, II, III…) on the homepage work-grid, and the numbered `01 / Vurdering`-style section indices used throughout — the system's clearest expression of "The Colour Index."

### FAQ Accordion
Square list items separated by hairline rules, italic Cormorant question text, gold-stroke plus icon that rotates 45° on open. Answer panel expands via `max-height` transition — flagged as a candidate for the same `grid-template-rows` fix used on OMEGA VVS BERGER, since `max-height` + `scrollHeight` reads cause the same layout-thrash pattern.

## Do's and Don'ts

### Do:
- **Do** keep DM Mono as the only body/label typeface, and Cormorant italic as the only headline/quote typeface — the contrast between them is the entire system.
- **Do** keep every corner square; a rounded element anywhere breaks the archival/index metaphor (see Shapes).
- **Do** ration gold to labels, rules, accents, and buttons — never a fill or large surface (The Rationed Gold Rule).
- **Do** convey depth with hairline rules and tint shifts, never `box-shadow` (The No-Shadow Rule).
- **Do** treat every current photo as a placeholder pending the real `@proffpaint_as` Instagram photo named in its HTML comment — see PRODUCT.md's Evidence on Hand.

### Don't:
- **Don't** introduce a card-with-shadow pattern; it directly contradicts this system's flat, rule-based depth language.
- **Don't** add a fourth section-background variant beyond `sec-tint` / `sec-clay` / `sec-dark`.
- **Don't** use gradient text, glassmorphism, or purple/neon gradients anywhere in this system.
- **Don't** add a section-label eyebrow to every single section uniformly — the numbered-index device already carries that role in this system; don't stack both.
