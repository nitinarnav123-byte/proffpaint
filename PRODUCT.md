# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Homeowners and property owners in Oslo and Viken (Ytre Enebakk, Asker, Nesodden, and surrounding municipalities) needing interior/exterior painting, sparkling (surface prep), wallpapering, or tiling. They weigh painters primarily on verified track record and communication reliability, then want a fast, concrete quote after a free site visit (befaring). They're deciding whether to book, not browsing for inspiration.

## Product Purpose

A single-page marketing and booking site for ProffPaint AS, a painting contractor founded by Oscar Buyukbas in Ytre Enebakk in 2017. It presents services (interior/exterior painting, sparkling, wallpapering, plus tiling and full-project coordination), a verified track record, a project gallery, and a two-path booking flow (Calendly + form). Success is a visitor trusting the track record enough to book a free site visit.

## Positioning

A-til-Å (A-to-Z) full-service coordination: Oscar is the single point of contact who brings in an established network of murer, tømrer, rørlegger, and elektriker as a project needs them, so the client deals with one contractor instead of managing several trades themselves. The verified review volume (413 completed jobs, 4.97/5 across 303 BankID-verified Mittanbud reviews) is the proof of this claim, not the positioning itself — a newer competitor could eventually match the review count, but the coordination model is the durable mechanism.

## Operating Context

- Norwegian-language, single-page site serving Ytre Enebakk and the wider Oslo/Viken region.
- Booking flow has two paths: a Calendly-embedded scheduler and a Formspree-backed contact/booking form, both with client-side validation.
- Visitors are typically planning a considered-purchase renovation project (not an emergency, unlike a plumber) — timeline expectations and price ranges in the FAQ matter more here than urgency-driven CTAs.

## Capabilities and Constraints

- Static HTML/CSS/JS site (no framework, no build step); client-side hash routing (`#hjem`, `#tjenester`, `#galleri`, `#bestilling`, `#om-oss`, `#kontakt`).
- Third-party dependencies: Calendly (scheduling), Formspree (form submission), Google Maps (embedded location), Instagram (`@proffpaint_as`, linked as the real photo source).
- No CMS — content changes require editing the HTML directly.
- No dedicated privacy/personvern page currently exists despite forms collecting personal data — an open gap, not a design decision.

## Brand Commitments

- Name: ProffPaint AS. Founder: Oscar Buyukbas, founded 2017 in Ytre Enebakk. Org.nr. 918 353 607 MVA.
- Editorial clay/gold visual identity: warm paper/clay backgrounds, italic Cormorant serif display, DM Mono for all body and label text — an unusual, deliberate choice that gives the site a cataloged, gallery-index character distinct from typical håndverker sites.
- Anti-references: generic tradesman-site clichés (stock blue/orange gradients, paint-roller icon grids), generic AI marketing tropes (glassmorphism, gradient text, hero-metric stat blocks, identical feature-card grids, eyebrow-over-every-section), anything reading as a templated "local business website builder" output.

## Evidence on Hand

- **Real:** the verified track record (413 completed jobs, 4.97/5 average across 303 BankID-verified Mittanbud reviews, matching the `AggregateRating` JSON-LD), the founding story (Oscar Buyukbas, 2017, Ytre Enebakk), org.nr, address, phone, business hours, and the customer testimonials.
- **Not real — placeholder, disclosed as such:** every photograph on the site is stock Pexels imagery. This was never hidden — the site's own HTML carries inline comments on every image (`<!-- replace with @proffpaint_as foto: ... -->`) flagging exactly what real photo should replace it. Future work must pull from the real `@proffpaint_as` Instagram account per those comments rather than adding more stock imagery or treating the current photos as final.

## Product Principles

1. **Verified track record at a glance.** The 413/4.97/303 numbers are the core trust signal and should stay immediately visible — they are real, audited-style proof in a category full of unverifiable claims.
2. **A-til-Å reads as the real edge.** The single-point-of-contact coordination model (bringing in murer, tømrer, rørlegger, elektriker as needed) should be legible as ProffPaint's actual differentiator, not just a service bullet among others.
3. **Frictionless path to befaring.** Both booking paths (Calendly, form) should stay equally easy — visitors evaluating a considered purchase often want to browse before committing to a specific time slot.
4. **Editorial precision over corporate gloss.** The clay/gold, mono-type, gallery-index aesthetic is the brand's actual differentiator visually; don't flatten it toward a generic tradesman template.
5. **Photography is an open task, not a finished asset.** Every image is a labeled placeholder; treat the gallery and hero photos as pending real work, not as content to build further around.

## Accessibility & Inclusion

Baseline: WCAG 2.1 AA:
- Strong color contrast (verify, don't eyeball) — especially DM Mono body text at small sizes against the warm clay/paper backgrounds.
- Large, clearly labeled tap targets for buttons and form fields.
- All interactive elements keyboard-navigable with visible focus states.
- `prefers-reduced-motion` respected for scroll-reveal and other animations.
- Norwegian-language content stays clear and jargon-free.
