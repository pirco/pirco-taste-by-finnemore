# Artisan Output Contract

> Inherits all foundation output contract requirements (HTML, CSS, component, performance, delivery). This file documents extensions and artisan-specific deliverable requirements.

---

## Product grids

- **2–3 columns maximum.** Never 4+. Two columns is the default for product grids on desktop.
- **Generous gaps.** Grid gap minimum 48px (`space-12`), recommended 64–96px (`space-16` to `space-24`). This is wider than foundation card grids.
- **Mixed aspect ratios permitted.** Unlike foundation (which requires consistent ratios within a grid), artisan product grids may intentionally mix ratios. When mixing, use CSS Grid with explicit row sizing or masonry layout, not Flexbox that would stretch images.
- **Product card content is minimal:** image, product name, price. No badges, no ratings, no secondary actions. The card links to the product page as a single clickable unit.
- **Masonry implementation:** use CSS `columns` or CSS Grid with `masonry` (with fallback to a staggered fixed-height approach for browsers without masonry support).

```css
/* Masonry fallback pattern */
.product-grid {
  columns: 2;
  column-gap: var(--space-16);
}

.product-grid .product-card {
  break-inside: avoid;
  margin-bottom: var(--space-16);
}

/* When CSS Grid masonry is supported */
@supports (grid-template-rows: masonry) {
  .product-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: masonry;
    gap: var(--space-16);
    columns: unset;
  }

  .product-grid .product-card {
    margin-bottom: 0;
  }
}
```

---

## Product detail pages

Required structure and hierarchy:

1. **Large hero image** — full-width or near-full-width. Minimum 60vh height on desktop. This is the first thing the visitor sees. `loading="eager"`, `fetchpriority="high"`.
2. **Product information block** — presented with generous spacing, not crammed into a sidebar:
   - Product name (display type, `text-3xl` to `text-5xl`)
   - Price (plain, no strikethrough "was/now" patterns unless client explicitly requests)
   - Brief description (1–3 sentences, written as prose, not bullet points)
   - Materials and/or dimensions (listed plainly, no expandable accordions for basic info)
3. **Image gallery as editorial sequence** — not a thumbnail carousel. Images are presented in a vertical scroll or a curated grid below the hero. Each image is large enough to appreciate detail. Lightbox is optional; if included, it should be a simple full-screen overlay with crossfade transitions.
4. **Single "Add to bag" action** — a button or text link. Not a sticky bar. Not accompanied by quantity selectors unless the product warrants it (buying multiples of a one-of-a-kind ceramic is unusual). Variant selection (size, color) should be minimal inline selectors, not a complex configuration panel.

---

## Explicitly excluded from artisan output

These elements must NOT appear unless the client explicitly requests them:

- **Product badges** ("Sale", "New", "Best Seller", "Limited Edition") — if a product is special, the photography and placement communicate that
- **Urgency mechanisms** — countdown timers, low-stock warnings ("Only 3 left!"), "selling fast" indicators
- **Social proof on product cards** — star ratings, review counts, "X people bought this"
- **Reviews on product cards** — reviews, if present, belong on the product detail page only, displayed as plain-text quotes (not star aggregates)
- **Quick-view modals** — every product deserves its own page
- **Cross-sell carousels** ("You may also like", "Complete the look", "Pairs well with") — if editorial product relationships exist, present them as a curated "Related" section with 2–3 items, styled identically to the main product grid
- **Promotional banners or announcement bars** — no "Free shipping over $X" bar, no seasonal sale banners
- **Newsletter popups or modals** — newsletter signup, if present, is an inline element in the footer or on a dedicated page

---

## Collection / category pages

- Feel like curated exhibitions, not filtered catalogs
- **Hero moment:** a full-bleed or large image that sets the collection's mood, with the collection name overlaid or below
- **Optional editorial intro:** 1–3 sentences describing the collection, the season, or the maker's intention
- **Product grid:** 8–16 products in a 2–3 column gallery layout with mixed aspect ratios
- **No filter sidebar.** If filtering is truly necessary (50+ products), use a minimal inline filter row with 3–4 options maximum (material, color, price range). No multi-select checkboxes, no accordion filter groups.
- **No sort dropdown.** The products are arranged in the order the brand intended. If sort is necessary, it is a single toggle: "Price: low–high / high–low"

---

## About / story page

- Tells the maker's story with editorial imagery
- Structure: hero image of the maker/studio, followed by long-form prose with interspersed images
- Images are not decorative — each shows a specific moment (workshop, material sourcing, process, finished work)
- No team grid with headshots. If the team is shown, it is through candid photography in context.
- No timeline of company milestones. If history matters, weave it into the narrative.

---

## Cart

- **Minimal slide-out panel or dedicated page** — not a modal
- Shows: product image (small), name, variant if applicable, price, quantity, remove option, subtotal
- No upsells, no "you might also like," no "add gift wrapping" checkbox
- Clear path to checkout — one button
- If the cart is empty, a simple message and a link back to the shop. No sad-face illustrations.

---

## Artisan design tokens (extending foundation)

```css
:root {
  /* Extended spacing for artisan generosity */
  --space-48: 12rem;   /* 192px */
  --space-60: 15rem;   /* 240px */

  /* Artisan display type — override per project */
  --font-display: 'Project Display Face', Georgia, serif;

  /* Artisan-adjusted timing */
  --transition-standard: 400ms;
  --transition-image: 600ms;
  --transition-page: 400ms;

  /* Artisan color bias — warm neutral defaults */
  --color-bg: #f6f4f0;          /* warm linen */
  --color-surface: #faf9f7;     /* lighter warm */
  --color-text-primary: #1c1917; /* warm near-black */
  --color-text-secondary: #57534e; /* warm gray */
  --color-text-muted: #a8a29e;    /* warm light gray */
  --color-border: #d6d3d1;
  --color-border-subtle: #e7e5e4;
}
```

---

## Performance adjustments

Foundation performance contract still applies with these artisan-specific adjustments:

- Image weight allowance: 300KB standard, 500KB hero/product detail (up from 200KB/400KB)
- Total page weight allowance: 700KB initial load (up from 500KB) to accommodate higher-quality product photography
- LCP target remains < 2.5s — the higher image budget must be managed with proper `srcset`, compression, and CDN delivery
- CLS target remains < 0.1 — mixed aspect ratios require explicit `width` and `height` attributes on every image
