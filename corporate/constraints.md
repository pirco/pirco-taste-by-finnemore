# Corporate / Institutional Constraints

Inherits all foundation constraints. This document specifies ONLY where corporate taste diverges. If a value is not listed here, the foundation value applies.

---

## Typography

**Divergences from foundation:**

- **Sans-serif only.** No display serifs, no editorial serif families. Institutional content demands neutral, high-legibility typefaces. The optional serif family permitted in foundation is not available here.
- **Tighter type scale.** Base size may be reduced to 15px for higher information density. The modular scale compresses slightly at the top — display headings rarely exceed `text-4xl` (48px). The goal is efficient use of vertical space without sacrificing readability.
- **Narrower weight range: 400–600.** Foundation permits heading weights up to 700. Corporate caps at 600 (semi-bold). Bold weights feel promotional in institutional contexts.
- **Liberal use of small sizes.** `text-sm` (14px) and `text-xs` (12px) are used more freely for metadata, labels, timestamps, breadcrumbs, utility navigation, and table headers. Foundation restricts 12px to captions/labels — corporate extends it to all supporting text within structured UI elements.

**What stays the same:** Line-height ranges, letter-spacing rules, system font fallback stack, max 2 families, underline-for-links-only rule.

---

## Spacing

**Divergences from foundation:**

- **Tighter section spacing: 96–128px** (`space-24` to `space-32`). Foundation uses 128–160px. Corporate sites carry more content per page and need to reduce vertical distance between major blocks. The visitor is scrolling through structured information, not experiencing a visual narrative.
- **Tighter component gaps: 24–48px** (`space-6` to `space-12`). Foundation uses 32–64px. Cards, content groups, and data sections sit closer together to support scanning.
- **Denser information layout.** Foundation's generous whitespace is appropriate for content-forward sites. Corporate sites may pack more elements per viewport height — sidebar + content layouts, multi-column lists, compact card grids — without violating the spacing scale.

**What stays the same:** 8px base grid, 4px sub-grid rule, element gap range (8–24px), all spacing values from the token scale.

---

## Layout

**Divergences from foundation:**

- **Stricter max-width: 1200px.** Foundation's standard max-width is 1280px. Corporate narrows to 1200px. Institutional content benefits from slightly tighter horizontal containment — it keeps dense information manageable and ensures comfortable line lengths even in multi-column layouts.
- **Sidebar layouts are a first-class pattern.** Content + sidebar at 1200px total: content area 2/3 (~800px), sidebar 1/3 (~400px). Sidebars carry contact information, related links, section navigation, key facts, and download lists. Foundation allows sidebars at 960px — corporate elevates them to a standard layout pattern.
- **Breadcrumb navigation required.** Every page below the homepage must include a breadcrumb trail. This is not optional. Breadcrumbs are the primary wayfinding mechanism for deep site structures.
- **Full-width background colors for section separation.** Content sections may use alternating background colors (e.g., white and cool off-white) that extend edge-to-edge while keeping content within the 1200px container. This provides visual separation in long pages without relying on excessive whitespace.

**What stays the same:** 12-column grid, breakpoints, prose max-width (680px), container padding scale, line-length limit (75 characters), no horizontal scroll rule.

---

## Color

**Divergences from foundation:**

- **Cool/neutral palette enforced.** Background off-whites shift cool: `#f8f9fa`, `#f1f3f5` instead of foundation's warm `#f8f7f4`. The palette reads as professional and institutional rather than artisanal or editorial.
- **Blues and cool grays preferred for accent.** The accent color defaults to a blue or blue-gray range. Cool greens and teals are acceptable. No warm tones (reds, oranges, warm yellows) unless explicitly mandated by the client's brand guidelines.
- **WCAG AAA (7:1) required for ALL text**, not just primary. Foundation requires 7:1 for `text-primary` but allows 4.5:1 for `text-secondary`. Corporate elevates the requirement: `text-secondary` must also meet 7:1. Only `text-muted` (used for non-essential metadata and disabled states) may use the 4.5:1 AA threshold.

**What stays the same:** Token set structure (all 10 tokens required), no pure black/white, max 5 active colors, color never sole state indicator, dark mode rules.

---

## Motion

**Divergences from foundation:**

- **Micro-interactions only.** Duration range is 100–200ms for everything. Foundation's standard (250–350ms) and dramatic (600–900ms) tiers are eliminated. No transition in corporate UI should take longer than 200ms.
- **No parallax.** Not "subtle parallax." None.
- **No scroll-triggered animations.** Content does not animate in on scroll. It is present when the viewport reaches it.
- **No hero animations.** No animated headlines, no motion on page load, no entrance choreography.
- **Prefer instant state changes with subtle easing.** Hover states, focus states, and active states should feel immediate. The easing is there to prevent jarring flickers, not to create a sense of motion.

**What stays the same:** `prefers-reduced-motion` required, no infinite animations, no load-blocking animation.

---

## Images

**Divergences from foundation:**

- **Informational, not atmospheric.** Images serve reference purposes: headshots of people, photos of facilities/campuses, charts, diagrams, infographics, event photos. No mood photography, no abstract textures, no lifestyle imagery unless documenting actual events.
- **Standard aspect ratios only: 16:9, 4:3, 1:1.** Foundation permits 3:2, 2:3, 3:4, and 21:9. Corporate restricts to the three most common ratios for consistency across directories, listings, and grids.
- **No full-bleed hero images.** Heroes are contained — text sits alongside or below the image within the 1200px container. No edge-to-edge photographic headers.
- **Tighter size budget: 150KB max per image.** Foundation allows 200KB standard, 400KB hero. Corporate reduces to 150KB for all images. Institutional pages often contain many images (directories, event listings, news) and cumulative weight matters.

**What stays the same:** WebP + fallback, `srcset` required, lazy loading below fold, `width`/`height` attributes, alt text required, no `background-image` for content images.

---

## Navigation

**Addition — not present in foundation:**

Corporate sites have navigation complexity that foundation does not address. These are new constraints, not overrides.

- **Mega-menu supported.** For sites with 50+ pages across multiple departments, mega-menus provide structured access to the full site tree. Mega-menu panels open on click (not hover), display organized link groups with clear section headings, and close on outside click or Escape key. Keyboard navigation must work fully within the mega-menu.
- **Utility navigation in a top bar.** A slim bar above the main header carries search, login/account, language selector, and audience selector (e.g., "Students | Faculty | Staff | Visitors"). This bar is visually distinct from the primary navigation — smaller type, lighter color, minimal height (32–40px).
- **Sticky header with reduced height on scroll.** The header sticks to the top on scroll but reduces in height (e.g., from 80px to 56px) to conserve screen space. The transition is instant or near-instant (100ms max). Logo may shrink or simplify.
- **Mobile: hamburger menu with full navigation tree.** On mobile viewports, the mega-menu collapses into a hamburger menu that reveals the full navigation tree with expandable sections. The menu is a full-viewport overlay, not a slide-in panel. Search is accessible at the top of the mobile menu.
