# Foundation Constraints

The dials that govern every Piroc project. Domain packages and client overrides may adjust these values, but the structure holds.

---

## Typography

**Scale** (modular, base 16px, ratio 1.25 — Major Third):
- `text-xs`: 12px
- `text-sm`: 14px
- `text-base`: 16px
- `text-lg`: 20px
- `text-xl`: 24px
- `text-2xl`: 30px
- `text-3xl`: 36px
- `text-4xl`: 48px
- `text-5xl`: 60px

**Line height:**
- Body text (≤20px): 1.5–1.6
- Sub-headings (24–36px): 1.3–1.4
- Display headings (≥48px): 1.05–1.15
- Never below 1.0. Never above 1.8.

**Letter spacing:**
- Body text: 0 (default)
- Sub-headings: -0.01em to -0.02em
- Display headings: -0.02em to -0.04em
- Uppercase text (when permitted): 0.05em to 0.1em
- Never positive letter-spacing on lowercase body text

**Font families:**
- Maximum 2 families per project (1 preferred)
- One sans-serif for body and UI is the default
- A display/serif family is optional, used only for headings or editorial moments
- System font stack as fallback always: `-apple-system, BlinkMacSystemFont, 'Segoe UI', system-ui, sans-serif`

**Hard rules:**
- No font size below 14px for body text (12px only for captions/labels)
- No light/thin weights below 20px
- Headings may use weight 500–700; body uses 400 (regular) with 500–600 for emphasis
- Underlines for links only. Never for decoration.

---

## Spacing

**Base unit:** 8px

**Scale:**
- `space-1`: 4px (half-unit — only for tight optical adjustments)
- `space-2`: 8px
- `space-3`: 12px
- `space-4`: 16px
- `space-6`: 24px
- `space-8`: 32px
- `space-10`: 40px
- `space-12`: 48px
- `space-16`: 64px
- `space-20`: 80px
- `space-24`: 96px
- `space-32`: 128px
- `space-40`: 160px

**Application:**
- Section spacing (between major content blocks): 128–160px (`space-32` to `space-40`)
- Component gaps (between cards, content groups): 32–64px (`space-8` to `space-16`)
- Element gaps (within a component): 8–24px (`space-2` to `space-6`)
- Text paragraph spacing: equal to line-height (typically 24px for body)

**Hard rules:**
- All spacing values must land on the 4px sub-grid (multiples of 4)
- No margin/padding values outside the scale without explicit justification
- Vertical rhythm takes precedence over horizontal alignment when they conflict

---

## Layout

**Grid:** 12-column with gutters

**Breakpoints:**
- `sm`: 640px
- `md`: 768px
- `lg`: 1024px
- `xl`: 1280px
- `2xl`: 1536px

**Max-widths by content type:**
- Prose/reading: 680px (38–42 characters per line at 16px)
- Content + sidebar: 960px
- Standard layout: 1280px
- Full-bleed: 100% (edge-to-edge, used sparingly)

**Container padding:**
- Mobile (< 640px): 16px (space-4)
- Tablet (640–1024px): 24px (space-6)
- Desktop (> 1024px): 32–48px (space-8 to space-12)

**Hard rules:**
- Prose line length must not exceed 75 characters
- Content must be reachable without horizontal scrolling at any viewport width
- Grid gutters: 16px mobile, 24px tablet, 32px desktop
- No layout shifts on load (reserve space for async content)

---

## Color

**Required token set** (every project must define these):
- `--color-bg`: Page background
- `--color-surface`: Card/component background
- `--color-text-primary`: Main body text
- `--color-text-secondary`: Supporting text, metadata
- `--color-text-muted`: Placeholder text, disabled states
- `--color-border`: Dividers, input borders
- `--color-border-subtle`: Light separators
- `--color-accent`: Primary interactive color (links, buttons, focus rings)
- `--color-accent-hover`: Accent interaction state
- `--color-accent-muted`: Accent at reduced opacity (backgrounds, tags)

**Contrast requirements:**
- `text-primary` on `bg`: minimum 7:1 (WCAG AAA for normal text)
- `text-secondary` on `bg`: minimum 4.5:1 (WCAG AA)
- `text-muted` on `bg`: minimum 3:1 (WCAG AA for large text / UI)
- `accent` on `bg`: minimum 4.5:1
- Interactive elements: visible focus ring with 3:1 contrast against adjacent colors

**Hard rules:**
- No pure black (`#000`) for text — use a near-black with slight warmth or coolness (e.g. `#1a1a1a`, `#111827`)
- No pure white (`#fff`) for backgrounds — use an off-white (e.g. `#fafafa`, `#f8f7f4`)
- Maximum 5 colors in the active palette (bg, text, accent + 2 supporting)
- Color must never be the sole indicator of state (always pair with shape, text, or icon)
- Dark mode: optional, but if implemented, must define the full token set independently

---

## Motion

**Duration ranges:**
- Micro-interactions (hover, focus, toggle): 100–200ms
- Standard transitions (fade, slide, expand): 250–350ms
- Dramatic transitions (page, hero, gallery): 600–900ms

**Easing:**
- Enter/appear: `cubic-bezier(0, 0, 0.2, 1)` — decelerate in
- Exit/disappear: `cubic-bezier(0.4, 0, 1, 1)` — accelerate out
- Move/resize: `cubic-bezier(0.4, 0, 0.2, 1)` — standard ease
- Spring-like (optional): `cubic-bezier(0.34, 1.56, 0.64, 1)` — subtle overshoot

**Hard rules:**
- `prefers-reduced-motion: reduce` must disable all non-essential animation. Essential = loading spinners, accordion expand/collapse. Everything else stops.
- No animation on page load that delays content visibility
- No infinite animations (except loading states)
- Scroll-triggered animations: trigger once, no replay on scroll-up
- Parallax: maximum 0.1 rate differential (subtle only). Disabled on mobile.

---

## Images

**Required aspect ratios** (use consistently within a project):
- Hero/banner: 16:9 or 21:9
- Card thumbnail: 3:2 or 4:3
- Square: 1:1 (avatars, icons, product shots)
- Portrait: 2:3 or 3:4

**Format and delivery:**
- WebP as primary format, JPEG/PNG fallback via `<picture>` element
- `srcset` widths: 640, 768, 1024, 1280, 1536, 1920
- `sizes` attribute required on all responsive images
- Lazy loading (`loading="lazy"`) on all images below the fold
- First visible image: `loading="eager"`, `fetchpriority="high"`
- Explicit `width` and `height` attributes to prevent layout shift

**Hard rules:**
- No uncompressed images served to the browser
- No images without `alt` text (decorative images get `alt=""` and `role="presentation"`)
- Maximum image weight: 200KB for standard images, 400KB for hero/full-bleed
- No background-image for content images (use `<img>` or `<picture>` for accessibility)
