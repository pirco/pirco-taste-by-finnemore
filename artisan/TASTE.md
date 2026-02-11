# Pirco Artisan Taste

Inherits from foundation. Extends it for boutique brands, studios, and curated e-commerce. Everything below documents ONLY divergences from foundation — if a value isn't mentioned here, the foundation value applies.

## Philosophy

The product is sacred — the site exists to honor it. Gallery logic over store logic. The experience of browsing should feel like visiting an atelier, not scrolling a marketplace. Curate ruthlessly: show 12 products beautifully rather than 100 adequately. Every product image should be worthy of framing. The site itself should feel handmade, considered, and unhurried. No urgency, no scarcity manipulation, no conversion-funnel psychology. The "add to cart" moment is a considered choice, not a clickthrough metric.

## Constraints (divergences from foundation)

**Typography:** Display type can be expressive — serifs, geometric sans, even handwritten for brand moments. Body stays foundation-standard. Display sizes extend to 72px. Letter-spacing on display text: -0.04 to -0.06em (tighter than foundation's -0.02 to -0.04em). Light weights (300) permitted at 48px+.

**Spacing:** Most generous of all packages. Section spacing: 160–240px (foundation: 128–160px). Component gaps: 48–96px (foundation: 32–64px). White space is the primary design element — it communicates luxury and care.

**Layout:** 2–3 column max for product grids (never 4+). Masonry layouts permitted. Asymmetric/staggered layouts encouraged. Mixed aspect ratios within a grid create visual tension. Full-bleed images alternate with contained compositions.

**Color:** Neutral foundation with one brand accent. Natural/organic palette bias (stone, linen, sage, clay). Off-whites with deliberate temperature (warm for handmade, cool for architectural). Minimal color — product images provide the palette.

**Motion:** Medium pace. Standard transitions 300–500ms (foundation: 250–350ms). Image hover: subtle zoom (1.02–1.05) or gentle opacity shift. Page transitions permitted (crossfade, 400ms). Scroll-triggered reveals: one element at a time, generous threshold, 500–700ms.

**Images:** Mixed aspect ratios as deliberate design choice (3:2, 2:3, 4:5, 1:1 in the same grid). Higher quality ceiling: 300KB standard, 500KB product detail (foundation: 200KB/400KB). Lifestyle shots alongside product shots. No white-background product photography unless that IS the brand.

**Navigation:** 3–4 items maximum. Logo + Shop + About + Contact. No categories in main nav unless 4 or fewer. Cart icon subtle, no badges. No announcement bars. Nav height ~60px. Mobile: slide-out or full-screen overlay.

## Behavior

Curate ruthlessly. Product pages are stories, not spec sheets. Let photography lead; design supports, never competes. Avoid mass-market e-commerce conventions: no badges ("Sale", "New"), no urgency timers, no "X people viewing this," no star ratings on product cards, no quick-view modals. When in doubt, choose the option a gallery or bookshop would choose. Collection pages are curated exhibitions, not filtered catalogs. The cart is quiet — no upsells, no cross-sells, no shipping progress bars.

## Output Contract (extends foundation)

Product grids: 2–3 columns, generous gaps (48–96px), mixed aspect ratios, masonry layout with CSS columns fallback. Product cards: image + name + price only. Product pages: large hero image, name at display scale, price, brief prose description, materials/dimensions as definition list, editorial image gallery, single "Add to bag" action. No product badges, urgency mechanisms, star ratings, quick-view modals, or cross-sell carousels unless explicitly requested. Cart: minimal slide-out or dedicated page. Collection pages: hero image, optional editorial intro, 8–16 products in gallery layout. About page: maker's story with editorial imagery. Performance: 700KB page weight budget (up from 500KB for photography), LCP < 2.5s, CLS < 0.1.

## Examples Summary

**Good patterns:** 2-column masonry product grid with mixed aspect ratios and product name + price only. Product detail with full-bleed hero, prose description, editorial image sequence, single "Add to bag" link. Homepage as single hero image + brand name + one line + "Shop" link. Navigation: logo + 3 text links + subtle cart icon, 60px total height.

**Bad patterns:** 4-column uniform grid with SALE badges, star ratings, quick-view overlays. Product detail with zoom tool, urgency banner, dual CTAs, cross-sell carousel, 47 reviews. Homepage with 5-slide carousel, category grid, "Best Sellers" section, press logo bar, newsletter popup. Three-row header with announcement bar, search, account/wishlist icons, mega-menu.

---

*Full documentation: philosophy.md, constraints.md, behavior.md, output-contract.md, examples.md, context.md*
