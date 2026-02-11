# Hospitality Output Contract

> Inherits all foundation output contract requirements. This document extends the contract for hospitality-specific deliverables. Foundation requirements (semantic HTML, accessibility, responsive meta, design tokens, reduced motion, performance targets) remain in full effect.

---

## Extended design tokens

Hospitality projects must extend the foundation `:root` token set with warm palette values and hospitality-specific tokens:

```css
:root {
  /* Warm palette — replaces foundation neutral defaults */
  --color-bg: #faf8f5;
  --color-surface: #ffffff;
  --color-text-primary: #1a1512;
  --color-text-secondary: #6b5e54;
  --color-text-muted: #a09489;
  --color-border: #d4c9be;
  --color-border-subtle: #e8e0d8;
  --color-accent: #b8953f;
  --color-accent-hover: #a07e2e;
  --color-accent-muted: #f0e6d0;

  /* Typography — serif display added */
  --font-body: 'DM Sans', -apple-system, BlinkMacSystemFont, 'Segoe UI', system-ui, sans-serif;
  --font-display: 'Playfair Display', Georgia, 'Times New Roman', serif;

  /* Extended type scale */
  --text-6xl: 4.5rem; /* 72px — hospitality hero headline */

  /* Extended spacing scale */
  --space-48: 12rem;  /* 192px */
  --space-50: 12.5rem; /* 200px */

  /* Dark section tokens */
  --color-dark-bg: #1a1512;
  --color-dark-surface: #2c2420;
  --color-dark-text: #f5f0eb;
  --color-dark-text-secondary: #c4b8ab;
  --color-dark-text-muted: #8a7e72;
  --color-dark-border: #3d342e;
}
```

---

## Hero section contract

Every hospitality page must open with a hero that:

1. **Uses a full-viewport or near-full-viewport image** — minimum `90vh` height on desktop. The image should feel cinematic, not cropped.
2. **Aspect ratio: 21:9** on desktop, adapting to 16:9 or 3:2 on mobile for usable image height.
3. **Text overlay is minimal** — property name or section title, optionally a single sentence. White or warm off-white text with sufficient contrast (use a subtle gradient overlay if needed: `linear-gradient(to top, rgba(26,21,18,0.5), transparent)`).
4. **Ken Burns animation permitted** — `transform: scale(1.0) to scale(1.05)` over 15–20 seconds. Must respect `prefers-reduced-motion`.
5. **No carousel dots or arrow controls** — if multiple hero images are needed, use a slow crossfade (8–12 second interval) or let the page present them sequentially.
6. **Booking CTA in the hero is a quiet link**, not a contrasting button overlaid on the image.

---

## Image grid contract

Image sections must follow editorial layout principles:

1. **Asymmetric/editorial grids** — not uniform thumbnail grids. Vary image sizes within the grid (one large + two small, or staggered offsets).
2. **Mixed aspect ratios** — combine 3:2, 2:3, and 16:9 within a single grid for visual rhythm.
3. **Generous gaps** — `48–80px` between grid items, wider than foundation's standard.
4. **No lightbox thumbnails** — images should be presented at viewing size, not as thumbnails that expand.
5. **Captions are optional** — when present, they are small, muted, and positioned below or beside the image, never overlaid.

---

## Room and suite pages

Each room or suite is presented as a narrative, not a product listing:

1. **Lead with a full-bleed atmospheric photograph** of the room — not a wide-angle real estate shot, but an experiential image (light through curtains, a detail of the bed linen, the view from the balcony).
2. **Room name as a display heading** — using the serif display font. Below: a short atmospheric sentence, not a feature list.
3. **Details follow the editorial layout** — photographs interspersed with brief text blocks. Amenities are presented as prose or quiet lists, not icon grids.
4. **Specifications (size, occupancy, bed type)** are presented as metadata — small, muted, positioned after the narrative content. They are reference information, not selling points.
5. **Rate information, if shown, is understated** — "From $X per night" in secondary text weight, not a price badge or callout.
6. **Reservation CTA** — a single, refined link: "Reserve this room" or "Check availability" — positioned after the full narrative, not competing with the imagery.

---

## Restaurant and dining pages

1. **Lead with atmosphere** — a single, beautiful photograph of the dining space or a signature dish in context (not a food-only product shot).
2. **Chef and philosophy** — a brief editorial block about the dining philosophy, not a biography.
3. **Menu access** — link to a properly formatted HTML menu page, not a PDF download. If a PDF is unavoidable, clearly label the file size and format.
4. **Hours and reservation** — presented quietly at the bottom of the section or in a sidebar. This is reference information that the guest looks for after being convinced.

---

## Gallery sections

1. **Curated editorial sequences** — images are arranged to tell a visual story (arrival, the room, the view, dining, departure) rather than dumped in a random grid.
2. **Varied sizing** — the gallery is not a uniform grid. Feature images should be 2x or 3x the size of supporting images.
3. **No thumbnails with "view larger"** — images are presented at a size that rewards looking. If a detail view is needed, clicking opens a clean overlay with the image at near-full-screen size, minimal chrome.
4. **Whitespace as pacing** — gaps between gallery images create rhythm. The gallery should feel like turning pages in a book, not scrolling through a phone's camera roll.

---

## Navigation contract — hospitality extension

1. **Header may be transparent** over the hero image, transitioning to a solid warm background (`--color-bg`) on scroll. The transition should be smooth (300–400ms).
2. **Property name in the header** uses the display serif font — this is one of the permitted uses.
3. **Navigation items: 4–6 maximum** — Rooms, Dining, Experiences, Gallery, About, Reserve (or similar). No mega-menus.
4. **"Reserve" or "Book"** appears in the nav but is styled as a text link, not a contrasting button. It may use the accent color for differentiation.

---

## Performance contract — hospitality adjustments

Foundation performance targets remain, with these accommodations:

- **Total page weight: < 800KB initial load** (foundation: 500KB) — justified by the image-forward nature of hospitality sites. This is a ceiling, not a target.
- **LCP: < 3.0s** (foundation: 2.5s) — the hero image is typically the LCP element; larger file sizes and Ken Burns animation may add overhead.
- **CLS: < 0.1** — unchanged. Reserve space for hero images with explicit dimensions or aspect-ratio CSS.
- Hero image should use `loading="eager"` and `fetchpriority="high"`.
- Below-fold images must still use `loading="lazy"`.
- Serve multiple image sizes via `srcset` — the higher quality ceiling does not mean serving 500KB images to mobile devices.

---

## Delivery format — hospitality additions

In addition to foundation delivery requirements:

1. **Include `@font-face` declarations** for the serif display font, with `font-display: swap` to prevent FOIT.
2. **Include a dark-section utility** — CSS class (`.section-dark`) that applies the dark token set for atmospheric sections.
3. **Comment hospitality-specific sections** — `<!-- Hero — cinematic -->`, `<!-- Room narrative -->`, `<!-- Editorial gallery -->` to distinguish from generic components.
4. **Image placeholder pattern** — for images that will be replaced with real photography, use a warm neutral placeholder (`--color-border-subtle` background) with the target aspect ratio, never a gray box or broken image icon.
