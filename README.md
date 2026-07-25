
# Grove & Grind — Website

A full, static, **JavaScript-free** website for Grove & Grind, a fictional
juice press and coffee roastery. Built with plain HTML5 and CSS3 only —
no frameworks, no build step, no scripts.

## Project structure

```
grove-and-grind/
├── index.html        Full single-page site (all sections)
├── css/
│   └── style.css      All styling, layout, and animation
└── README.md          This file
```

## How to view it

No build tools or server required.

1. Open `index.html` directly in any modern browser (double-click it, or
   drag it into a browser window).
2. Or serve it locally, e.g. `python3 -m http.server` from inside the
   project folder, then visit `http://localhost:8000`.

The page loads three Google Fonts over the network (Fraunces, Work Sans,
Space Mono). If you're offline, the browser falls back to the system
serif/sans-serif/monospace stack defined in `style.css`, so the page still
works — it just looks slightly different.

## What's on the page

- **Header/nav** — sticky, with a fully CSS-only mobile menu (checkbox
  hack — no script needed to open/close it on small screens).
- **Hero** — brand statement plus an animated CSS "blob" (pure CSS
  `border-radius` keyframe animation, no JS, no image assets).
- **Marquee strip** — infinite-scroll CSS keyframe ticker of shop facts.
- **Our Story** — brand narrative and three value props.
- **Juice menu** — 7 cold-pressed juices with ingredients, size, and price.
- **Coffee menu** — espresso bar and filter/cold bar items.
- **Signature Crossovers** — 4 drinks that combine the juice press and the
  roaster (e.g. cascara + orange juice).
- **Process** — two parallel step-by-step tracks: "Grove to Glass" (juice)
  and "Bean to Brew" (coffee). Numbered steps are used here deliberately,
  because the content is a genuine sequential process.
- **Testimonials** — three customer quotes.
- **Locations** — two fictional shop locations with hours and contact info.
- **Newsletter signup** — a static, styled `<form>`. It has no backend, so
  submitting it does nothing (see "Forms are non-functional" below).
- **Footer** — sitemap links and shop info.

All copy, menu items, prices, and locations are original placeholder
content written for this project — swap them for the real shop's details
before going live.

## Design system

- **Color** — deep forest ink (`#16261C`), warm paper cream (`#F7EFDC`),
  citrus-pulp yellow (`#F5B939`), blood-orange (`#E8611F`), and leaf green
  (`#7A9B5E`), plus a roasted espresso brown (`#2E1B12`) for the footer and
  coffee-menu accents. Defined as CSS custom properties at the top of
  `style.css` (`:root`) so the whole palette can be re-themed in one place.
- **Type** — Fraunces (display serif, used for headlines) paired with Work
  Sans (body copy) and Space Mono (labels, prices, eyebrows) for a
  menu-board feel.
- **Signature element** — the "Grove to Glass / Bean to Brew" dual-track
  diagram, showing the shop's two crafts as parallel, mirrored processes.
- Fully responsive down to small mobile widths (breakpoints at 980px,
  720px, and 480px).
- Visible keyboard-focus states on every interactive element.
- Respects `prefers-reduced-motion` — all animations are disabled for
  users who request it.

## Forms are non-functional (by design)

The newsletter form in the site has no JavaScript and no server to send
data to, so it will not actually subscribe anyone. To make it work, you
have two realistic options:

1. **Third-party form service** (fastest): point the `<form action="...">`
   at a service like Formspree, Getform, or Mailchimp's hosted signup
   form — most of these work with a plain HTML `<form>` and no JS.
2. **Your own backend**: replace `action="#"` with your endpoint URL and
   remove `onsubmit="return false;"` from the `<form>` tag in
   `index.html`.

## Customizing

- **Colors/fonts**: edit the custom properties in the `:root` block at the
  top of `css/style.css`.
- **Menu items/prices**: edit the `.menu-item` and `.sig-card` blocks in
  `index.html` — each is plain, repeated markup.
- **Locations/hours**: edit the `.loc-card` blocks in the Locations
  section.
- **Real photography**: the hero visual, about section, and map are all
  built from CSS gradients/shapes rather than image files, so there's
  nothing broken to fix — but you can swap any of them for real photos by
  replacing the relevant `<div>` with an `<img>` tag.

## Browser support

Built on standard, widely-supported CSS (Grid, custom properties,
`clamp()`, `backdrop-filter`). Tested against current versions of Chrome,
Firefox, Safari, and Edge. `backdrop-filter` on the sticky header
degrades gracefully to a solid background on browsers that don't support
it.
