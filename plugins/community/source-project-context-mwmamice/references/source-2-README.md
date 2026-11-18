# PG GROUP Design System

A reusable OpenDesign design-system package extracted from the **PG Group web** prototype (OpenDesign project f235d4e9). It is a strictly black-and-white editorial system for a Czech advertising production agency.

## Product Overview

PG GROUP (PG group a.s., Praha) is a **service and production advertising agency** with 30+ years on the market and 50+ steady clients. The website is its portfolio and contact channel. It provides proof of execution through case studies for brands such as BACARDÍ, MARTINI, BMW, FedCup and L'ORÉAL. The product's primary surfaces are:

- a homepage with a hero claim, client marquee, work cards, services accordion and inverse CTA;
- a filterable **Realizace** (work) index and case-study detail pages with a sticky params sidebar and engagement-scope tooltips;
- **Služby** (services) with a numbered accordion and a "Servisní spolupráce" benefit grid;
- **O nás** (team) and **Kontakt** (giant e-mail/phone links, copy-to-clipboard billing data, map).

The site supports light and dark themes and a CZ/EN switch (EN content pending). It deliberately includes no forms: conversion happens through direct e-mail and phone.

## Source Context

- `context/source-context.md`: the original handoff manifest (source project id, metadata, copied files).
- `context/provenance.md`: how each part of this package maps to the source evidence, and which evidence was superseded.
- `brand-spec.md`: the client-approved token table (hex → OKLch), fonts and five visual rules. **Canonical.**
- Screenshots: `image-12.png` and `image-6.png` show the final B&W hero. `image.png`–`image-5.png` and `image-9.png` are full-page captures of the earlier draft (teal accent confirmed in `image.png`, `image-3.png`, `image-9.png`), kept as layout and copy evidence only. `image-7.png` is the logo, `image-8.png` the client's stat strip, `image-10.png` an outlined-numeral reference, and `image-11.png` a browser capture of the narrow-wrapping hero bug that led to the full-width `.hero-wide` rule.

## Package Contents

| Path | What |
|---|---|
| `DESIGN.md` | Canonical rules: context, color, typography, spacing/layout, components, motion, voice, anti-patterns |
| `colors_and_type.css` | Reusable tokens: light/dark color, Montserrat + Mynerve type scale, spacing scale, radius, motion. Imports Google Fonts |
| `SKILL.md` | Agent-facing usage instructions |
| `assets/pg.css` | Preserved full component stylesheet from the source (header, work card, chips, ztag, accordion, benefits, CTA, big-link, copy, footer, responsive and reduced-motion rules) |
| `assets/pg.js` | Preserved source interactions (theme, language, sticky header, mobile menu, copy, tooltips, accordion, filters, cursor bubble, reveals) |
| `assets/logo-pg.png` | Preserved PG GROUP mark (178×140, used as a CSS mask) |
| `assets/img/` | Preserved, licensed **placeholder** photography (Wikimedia/Unsplash), with attribution in `assets/img/CREDITS.md` |
| `preview/` | Focused review cards (see manifest below) plus the shared `preview/preview.css` frame |
| `ui_kits/app/` | Applied React UI kit: `index.html` plus `components/*.jsx` composing a working four-view site |
| `homepage.html`, `realizace.html`, `reference-*.html`, `sluzby.html`, `o-nas.html`, `kontakt.html`, `to-se-jen-tak-nevidi.html`, `styleguide.html`, `index.html` | **Preserved source examples**: the complete prototype pages, still wired to `assets/pg.css` + `assets/pg.js` |

The package has no `fonts/` directory: the source loads Montserrat and Mynerve from Google Fonts (latin-ext) and ships no font binaries. It has no `build/` directory either, because the source has no runtime or app icons.

## Preview Manifest

| Card | Shows |
|---|---|
| `preview/colors-primary.html` | Light tokens, accent-as-inversion pairing, derived color-mix greys |
| `preview/colors-dark-mode.html` | Light and dark token sets side by side with live buttons and chips |
| `preview/typography-specimens.html` | Full Montserrat scale, label/tabular numerals, Mynerve script claim, note and closing claim |
| `preview/spacing-tokens.html` | 8px spacing scale, `.grid-1-2` split, `.why` ruled columns |
| `preview/radius-shadows.html` | 2px radius vs circles, no shadows, rule weights, focus ring |
| `preview/components-buttons.html` | Primary/secondary default and hover, disabled, link-arrow, icon/theme/segmented, inverse variants |
| `preview/components-navigation.html` | Header default and scrolled, mobile menu, filter chips, breadcrumbs, pager, ztag tooltips |
| `preview/components-work-cards.html` | Big and small work cards using the real portfolio photos, `.ph` placeholder |
| `preview/components-services-accordion.html` | Interactive numbered accordion plus benefits grid |
| `preview/components-contact-footer.html` | Big links, copy buttons, full inverse footer with Instagram strip and ghost wordmark |
| `preview/brand-assets.html` | `assets/logo-pg.png` raw and masked (light, inverse, dark), wordmark, marquee stand-ins, photography, team portraits |
| `preview/applied-surfaces.html` | Hero + pillars + CTA composition and live thumbnails of the preserved source pages |

## Review Workflow

1. Open `preview/brand-assets.html` and `preview/colors-primary.html` to confirm the B&W identity and logo.
2. Inspect `preview/typography-specimens.html`, then the `preview/components-*.html` cards; hover everything, since hover states are part of the spec.
3. Open `ui_kits/app/index.html` and click through Úvod → Realizace (filters) → Služby (accordion, "Zobrazit realizace" pre-filters) → Kontakt. Toggle the theme and CZ/EN.
4. For new work, load `colors_and_type.css` then `assets/pg.css`, reuse the class names documented in `DESIGN.md`, and copy components from `ui_kits/app/components/`.
5. Before production, replace the placeholder photography and the typographic client wordmarks with the client's own assets, and keep `assets/img/CREDITS.md` in sync.
