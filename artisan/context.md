# Artisan Context References

> Inherits all [foundation context references](../foundation/context.md). The references below are specific to artisan taste — boutique brands, studios, and curated e-commerce.

---

## Primary references

- **Miska Studio** (miskastudio.com) — The primary reference for artisan taste. Boutique ceramics e-commerce that treats product presentation with gallery sensibility. Mixed aspect ratios in the product grid, generous whitespace, minimal navigation, photography-forward pages. The product detail pages read like editorial spreads, not spec sheets. Study the spacing between elements, the restraint in the color palette, and how the grid rhythm alternates between tight and generous. This is what "curated, not cataloged" looks like.

- **Jonas Luebbers** (jonasluebbers.com) — Creative developer whose aesthetic and technical approach inspires the artisan taste system. Content-forward layout, quiet motion, gallery-like presentation. Luebbers' work for Miska Studio is the direct origin of many artisan constraints. Pay attention to how his sites breathe — the spacing is the design.

---

## E-commerce references

- **Aesop** (aesop.com) — Product presentation elevated to editorial art. Each product page is a composition, not a template. The color palette recedes to let product packaging and photography lead. Navigation is minimal. The browsing experience feels like walking through a well-designed retail space. Study the product detail page structure and the restraint in the category pages.

- **Hostem** (hostem.co.uk) — Fashion retail with gallery logic. Products are presented as art objects. The grid uses mixed aspect ratios and asymmetric layouts. Product pages feature editorial photography that tells the story of the garment in context. No badges, no urgency, no star ratings. The cart experience is quiet and considered. A reference for how fashion e-commerce can feel like a curated exhibition.

- **Hay** (hay.dk) — Scandinavian design retail that remains product-forward despite a large catalog. Clean grid, generous spacing, photography that shows products in lived-in environments. Study how Hay manages a bigger inventory while maintaining editorial sensibility — collection pages are curated stories, not filtered lists.

- **The Line** (theline.com) — Curated home goods with an editorial approach. Each collection is presented as a story with context, not just a grid of products. The buying experience feels like receiving a recommendation from someone with impeccable taste. Study the relationship between editorial content and product presentation.

---

## Editorial and hybrid references

- **Monocle** (monocle.com) — The reference for editorial commerce hybrid. Monocle blends magazine content with a shop, and neither feels subordinate to the other. The typography is confident. The grid is clean but not sterile. Products are presented with the same editorial rigor as articles. Study how commerce and content coexist without the site feeling like it's selling something on every page.

---

## Aesthetic principles drawn from these references

1. **Product images are the design.** Every reference site above uses photography as the primary design material. The site's job is to present those images with maximum impact and minimum interference.

2. **Navigation is almost invisible.** None of these sites have more than 4-5 top-level nav items. Most have 3. The navigation exists to orient, then disappears.

3. **Whitespace communicates value.** Generous spacing is not wasted space — it is the visual language of care and quality. Every reference site uses more whitespace than feels "efficient." That's the point.

4. **The grid has personality.** Not a rigid 4-column grid but a composed layout that mixes sizes, ratios, and spacing to create rhythm. The grid itself is a design decision, not a default.

5. **Commerce is understated.** Prices are present but not emphasized. "Add to cart" exists but doesn't shout. The purchase flow is smooth but not optimized for conversion at the expense of experience. These sites trust their products enough to let the visitor come to their own decision.

---

## Technical references (artisan-specific)

- **CSS Grid masonry layout** — The masonry approach used in artisan product grids. Follow the progressive enhancement pattern: CSS `columns` as baseline, CSS Grid masonry when supported.
- **View Transitions API** — For smooth page transitions in artisan sites. Use with restraint: simple crossfade only, 400ms duration. Progressive enhancement — the site works without transitions.
- **Intersection Observer** — For scroll-triggered reveals. One element at a time, generous threshold (0.2–0.3), no replay. The technical mechanism behind the unhurried reveal of product grids.
