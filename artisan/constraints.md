# Artisan Constraints

> Inherits all foundation constraints. This file documents ONLY divergences and extensions. If a value is not listed here, the foundation value applies.

---

## Typography

**Divergences from foundation:**

- Display type can be expressive. Serifs, geometric sans-serifs, and even handwritten faces are permitted for brand moments (hero headlines, product names, pull quotes). The foundation preference for a single sans-serif body face still holds — expressiveness is reserved for display sizes.
- Body text stays readable and follows foundation rules without exception. The display face is where brand personality lives.
- Larger display sizes permitted: the scale extends to 72px (`text-6xl: 72px`) for hero moments and product detail headlines. Use sparingly — one instance per page maximum.
- More dramatic letter-spacing on display text: -0.04em to -0.06em (foundation allows -0.02 to -0.04em). This tighter tracking creates the refined, high-end feel appropriate for artisan brands.
- Display weights can extend to 300 (light) at large sizes (48px+). Foundation restricts light weights below 20px; artisan permits them at display scale where legibility is not a concern.

**What stays the same:** Body type scale, line-height rules, max 2 font families, minimum font sizes, body weight rules.

---

## Spacing

**Divergences from foundation:**

- Most generous spacing of all packages. White space is the primary design element — it communicates luxury, care, and unhurried attention.
- Section spacing (between major content blocks): 160–240px (`space-40` to `space-60`). Foundation uses 128–160px. This is the single most visible artisan difference.
- Component gaps (between cards, product items, content groups): 48–96px (`space-12` to `space-24`). Foundation uses 32–64px.
- Element gaps remain foundation standard (8–24px) — over-spacing at the micro level looks broken, not refined.

**Extended scale values** (add to foundation scale):
- `space-48`: 192px
- `space-60`: 240px

**What stays the same:** 8px base grid, 4px sub-grid rule, element gap range, paragraph spacing.

---

## Layout

**Divergences from foundation:**

- Gallery-oriented grids replace the standard 12-column approach for product display. The underlying 12-column system still exists for page structure, but product presentation uses purpose-built gallery layouts.
- **2–3 columns maximum for product grids.** Never 4+. At artisan scale, each product needs enough visual real estate to be appreciated. Two columns is the default; three is the maximum for smaller items.
- **Masonry layouts permitted.** Foundation expects consistent aspect ratios within a grid. Artisan embraces mixed heights — masonry creates visual tension and a more organic, gallery-like feel.
- **Asymmetric and staggered layouts encouraged.** Products don't need to sit on the same baseline. A deliberate vertical offset (40–80px) between adjacent columns creates rhythm and guides the eye downward.
- **Mixed aspect ratios within a single grid** are a deliberate design choice, not an error. A 3:2 landscape next to a 2:3 portrait next to a 1:1 square creates the visual tension that makes a gallery feel curated rather than automated.
- **Full-bleed images alternate with contained compositions.** A product grid might be contained at 1280px, followed by a full-bleed lifestyle image, followed by a single product at 680px. This rhythm of expansion and contraction keeps the scroll experience dynamic.
- Standard max-width remains 1280px for contained content. Full-bleed sections have no max-width constraint.

**What stays the same:** Breakpoints, prose max-width (680px), container padding, line-length rules, no horizontal overflow.

---

## Color

**Divergences from foundation:**

- **Neutral foundation with one brand accent.** The artisan palette is deliberately restrained — the product images provide the color. The site itself recedes.
- **Natural/organic palette bias.** Default to colors found in materials: stone, linen, sage, clay, slate, parchment, ivory, charcoal. Avoid colors that feel synthetic or digital (saturated blues, electric purples, neon greens).
- **Off-whites carry temperature.** The `--color-bg` choice is critical: a warm off-white (cream, linen) for organic/handmade brands; a cool off-white (stone, ash) for architectural/minimal brands. This temperature sets the entire emotional tone.
- **Minimal use of color** beyond the product images. Accent color is used for interactive elements only (links, focus states, cart icon). No colored backgrounds, no gradient sections, no colored text blocks.
- **Product images are the color palette.** When a brand's ceramics are earth-toned, the site's neutrals should complement, not compete. When a brand's textiles are vivid, the site should be even more restrained to let the vibrancy speak.

**What stays the same:** Token structure, contrast requirements (AAA for primary text), no pure black/white rule, max 5 active colors, dark mode rules.

---

## Motion

**Divergences from foundation:**

- **Medium pace overall.** Artisan motion is slower and more deliberate than foundation defaults. Nothing snaps; everything eases.
- Standard transitions: 300–500ms (foundation uses 250–350ms). The additional time creates a sense of quality and consideration.
- **Image hover:** subtle zoom (scale 1.02–1.05) or gentle opacity shift (1.0 to 0.92). Pick one approach per project and use it consistently. Never both simultaneously.
- **Page transitions permitted** if smooth and purposeful. Crossfade between pages at 400ms is the reference. No slide, no wipe, no parallax page transitions. If page transitions add perceived load time, remove them.
- **Scroll-triggered reveals** at slow pace. One element at a time, not groups. Generous trigger threshold (element should be 20–30% visible before animation begins). Fade-up with 20–30px of travel, 500–700ms duration. Once per element — no replay on scroll-up.
- **Gallery/lightbox transitions:** 400–600ms crossfade between images. No slide carousel. Images appear, they don't fly in.

**What stays the same:** `prefers-reduced-motion` required, no infinite animations, no load-blocking animation, easing curves.

---

## Images

**Divergences from foundation:**

- **Mixed aspect ratios as a deliberate design choice.** Foundation requires consistent ratios within a project. Artisan intentionally mixes 3:2, 2:3, 4:5, 5:4, 1:1 within the same grid. This is the gallery aesthetic — each image is cropped to its own ideal composition, not forced into a uniform container.
- **Product photography is hero content.** Higher quality ceiling: 300KB for standard product images, 500KB for product detail heroes and lifestyle shots. The 200KB/400KB foundation limits are too restrictive for photography-driven sites where image quality IS the design.
- **Lifestyle and context shots alongside product shots.** A ceramic vase is shown alone AND on a shelf with books and light. A garment is shown flat AND worn AND in motion. The product exists in a world, not a void.
- **No product photos on white backgrounds** unless that IS the brand aesthetic (rare). Default to environmental photography — natural light, textured surfaces, lived-in spaces. The background is part of the story.
- **Image sequences tell editorial stories.** On a product detail page, the image gallery is not "front, back, side, detail" documentation. It is an editorial sequence: mood shot, full product, detail of material, product in use, scale reference. Each image has a purpose in the narrative.
- **Aspect ratio mixing guide for grids:**
  - 2-column grid: pair landscape (3:2) with portrait (2:3) for maximum tension
  - 2-column grid: pair square (1:1) with 4:5 portrait for subtle variation
  - 3-column grid: use consistent ratios OR one outlier that breaks the pattern intentionally
  - Never mix more than 3 different ratios in a single grid section

**What stays the same:** WebP + fallback, srcset required, lazy loading, explicit dimensions, alt text required, no uncompressed images.

---

## Navigation

**Divergences from foundation:**

Foundation suggests 3 items; artisan codifies minimal navigation as a hard rule.

- **3–4 items maximum** in the primary navigation. The canonical set: Logo + Shop + About + Contact. Variations: Logo + Collection + Studio + Contact. Logo + Shop + Story + Visit.
- **No categories in main navigation** unless the brand has 4 or fewer categories. If the brand has more, categories live on the shop page, not the nav. Navigation is for site sections, not product taxonomy.
- **Cart icon: subtle, not badge-heavy.** A simple bag or cart outline. Item count shown as a small, unobtrusive number — no colored badge, no bouncing animation, no "1 item in your cart!" tooltip.
- **Mobile navigation:** simple slide-out panel or full-screen overlay with generous typography. No hamburger icon with nested accordion menus. No bottom tab bar. The mobile nav should feel like a moment of pause, not a utility drawer.
- **Navigation height:** ~60px maximum. The nav should be felt, not seen. It exists to orient, then disappear.
- **No announcement bars, promotional banners, or secondary navigation rows** above the main nav. One row. That's it.
