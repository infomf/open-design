---
name: pg-group-design-system
description: Strict black-and-white editorial design system for PG GROUP, a Czech service and production advertising agency. Montserrat 900 display, Mynerve handwritten accent, inversion as the only accent, 1px rules, grayscale photography. Use for PG GROUP web pages, case studies, decks and prototypes.
user-invocable: true
---

# PG GROUP design system

**How to use:** load `colors_and_type.css` then `assets/pg.css`, follow `DESIGN.md`, and compose from `ui_kits/app/components/`.

## What is inside

- `DESIGN.md`: canonical rules covering color, typography, spacing/layout, components, motion, voice and anti-patterns.
- `colors_and_type.css`: tokens for light/dark color, the type scale, spacing, radius and motion.
- `assets/pg.css` and `assets/pg.js`: the full preserved component stylesheet and interactions from the source prototype.
- `assets/logo-pg.png`: the PG GROUP mark, applied as a CSS mask. `assets/img/`: licensed placeholder photos (see `CREDITS.md`).
- `preview/`: focused review cards for colors, typography, spacing, radius, components, brand assets and applied surfaces.
- `ui_kits/app/`: a React UI kit (Header, WorkCard, FilterChips, ServiceAccordion, CtaBlock, Footer, App).
- Root `*.html` pages: preserved source examples of every page of the prototype.

## Source Context

Based on the OpenDesign project "PG Group web" (f235d4e9): ten prototype pages, a shared CSS/JS bundle, a client brand spec (`brand-spec.md`) and review screenshots. The client's earlier teal-accented drafts are superseded by the brand spec. See `context/provenance.md` for the evidence map.

## When to use

- When building or extending PG GROUP web pages, case studies (realizace), service pages or landing pages.
- For prototypes, mockups and presentation artifacts that must look like PG GROUP.
- When production front-end code needs the exact token values or component class names.

## How to use

1. Link `colors_and_type.css` (which imports Montserrat and Mynerve), then `assets/pg.css`. Add `assets/pg.js` for static pages, and set `data-theme` on `<html>`.
2. Build pages from the documented classes: `.container`, `.section`, `.grid-1-2`, `.sec-head`, `.work-card`, `.svc`, `.benefits`, `.cta-block.inverse`, `.big-link`, `.ftr.inverse`.
3. For React prototypes, copy `ui_kits/app/components/*.jsx` and `data.js`; see `ui_kits/app/README.md`.
4. Check the result against the `preview/` cards and the anti-patterns in `DESIGN.md`.
5. Copy is Czech with vykání. Insert `&nbsp;` after single-letter prepositions.

## Design System Highlights

- **Colors:** pure greys only (#FFFFFF, #F4F4F4, #0A0A0A, #6B6B6B, #E2E2E2). The accent is surface inversion, and the dark theme mirrors light. Colour appears only when a grayscale photo is hovered.
- **Typography:** Montserrat 900 display at up to 96px (−0.02em), body at 400 / 16–18px / 1.6, and Mynerve script at most twice per screen (claim, notes).
- **Spacing and layout:** an 8px scale (`--s1`…`--s16`), a 1280px container and a 1fr/2fr editorial split. Sections open with a 2px ink rule and rows divide with 1px lines.
- **Radius and shadows:** a 2px radius, circles only for icon buttons and `.go` discs, and no shadows.
- **Interaction:** a single ease `cubic-bezier(.2,.7,.1,1)`. Arrows nudge 6px, titles shift 10px, discs rotate −45°, and photos zoom to 1.05 and regain colour. Both colours swap on hover, and every element has a focus-visible ring.
- **Icons:** thin 1.8px stroke line icons in `currentColor`, inside 44px outlined circles. No emoji.
