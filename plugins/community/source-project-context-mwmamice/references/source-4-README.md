# PG GROUP — applied UI kit

A working React composition of the PG GROUP web components. It is a four-view site (Úvod, Realizace, Služby, Kontakt) with live filters, an accordion, theme and language switching, a mobile menu and copy-to-clipboard.

## Structure

| File | Role |
|---|---|
| `index.html` | Entry: loads `../../colors_and_type.css`, `../../assets/pg.css`, React 18.3.1, ReactDOM and Babel standalone 7.29.0, then mounts `<App />` |
| `components/data.js` | Content fixtures copied from the source pages (work items, filters, services, benefits, contact, Instagram photos) on `window.PG_DATA` |
| `components/Header.jsx` | Sticky header, nav with `aria-current`, CZ/EN `.seg`, theme toggle, burger and full-screen inverse `.mnav` (Esc closes) |
| `components/WorkCard.jsx` | `.work-card` (big 4:5 / small 16:10) and `EngagementTag` (`.ztag` with tap-toggle tooltip) |
| `components/FilterChips.jsx` | `.filters` chips with counts, single-select, empty categories disabled |
| `components/ServiceAccordion.jsx` | Numbered `.svc` accordion whose "Zobrazit realizace" link pre-filters the work view, plus `Benefits` grid |
| `components/CtaBlock.jsx` | Inverse `.cta-block` with ghost "PG" and the page's single primary button |
| `components/Footer.jsx` | Inverse footer: Instagram strip, contact grid, `CopyButton`, socials, SVG wordmark |
| `components/App.jsx` | Views (`Hero`, home, work, services, contact) and state for route, filter, theme and language (persisted in `localStorage`) |

## Usage

1. Serve the package over HTTP (the OpenDesign preview does this); Babel standalone fetches the `.jsx` files.
2. To reuse a component, copy its `.jsx` file and load it after React and Babel. Every file exposes its components on `window` via `Object.assign`.
3. Always load `colors_and_type.css` and `assets/pg.css` first. The components only emit the source class names and contain no styling of their own.
4. Compose new pages by passing `PG_DATA`-shaped objects into `WorkCard`, `ServiceAccordion` and the other components, and keep one `CtaBlock` (one primary button) per view.

## Design Notes

- Based on the source prototype (`homepage.html`, `realizace.html`, `sluzby.html`, `kontakt.html`) and `assets/pg.css`. The layout, colors, typography and tokens are unchanged.
- `assets/pg.js` is **not** loaded here. Its behaviour (theme, menu, accordion, filters, copy, tooltips) is reimplemented in React state, because pg.js binds to the DOM once at load. The `.js-motion` line reveals and the cursor bubble are intentionally omitted.
- The kit adds only a few `kit-*` helpers in `index.html` (pillar strip, 3-column small-card grid, result count, empty state).
- Photos are licensed placeholders (`assets/img/CREDITS.md`), and `@[instagram účet PG]` is an honest placeholder.
