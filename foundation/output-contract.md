# Foundation Output Contract

The required shape and quality of every deliverable. Domain packages may extend this contract but never weaken it.

---

## HTML requirements

Every page or component must include:

1. **Semantic structure** — Correct use of landmark elements (`<header>`, `<nav>`, `<main>`, `<footer>`, `<aside>`). Heading hierarchy (`h1` → `h2` → `h3`) without skipping levels.

2. **Accessible markup** — All interactive elements are keyboard-focusable. Form inputs have associated `<label>` elements. Images have `alt` attributes. ARIA attributes used only when native semantics are insufficient.

3. **Responsive meta** — `<meta name="viewport" content="width=device-width, initial-scale=1">` present. No fixed-width layouts.

4. **Language attribute** — `<html lang="en">` (or appropriate language code).

5. **No inline styles** — All presentation in CSS. Exception: dynamic values set via CSS custom properties in `style` attributes.

---

## CSS requirements

1. **Design tokens** — All color, spacing, and typography values reference CSS custom properties defined in a `:root` block:

```css
:root {
  /* Color tokens */
  --color-bg: #f8f7f4;
  --color-surface: #ffffff;
  --color-text-primary: #1a1a1a;
  --color-text-secondary: #4a4a4a;
  --color-text-muted: #8a8a8a;
  --color-border: #d4d4d4;
  --color-border-subtle: #e8e8e8;
  --color-accent: #2563eb;
  --color-accent-hover: #1d4ed8;
  --color-accent-muted: #dbeafe;

  /* Typography tokens */
  --font-body: -apple-system, BlinkMacSystemFont, 'Segoe UI', system-ui, sans-serif;
  --font-display: var(--font-body);

  /* Spacing tokens */
  --space-1: 0.25rem;
  --space-2: 0.5rem;
  --space-3: 0.75rem;
  --space-4: 1rem;
  --space-6: 1.5rem;
  --space-8: 2rem;
  --space-12: 3rem;
  --space-16: 4rem;
  --space-24: 6rem;
  --space-32: 8rem;
  --space-40: 10rem;
}
```

2. **Reduced motion** — A `prefers-reduced-motion` media query that disables non-essential animations:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

3. **Mobile-first breakpoints** — Base styles for mobile, `@media (min-width: ...)` for larger viewports.

4. **No `!important`** — Exception: the reduced-motion reset above and third-party overrides.

---

## Component requirements

Every component (hero, card, nav, footer, form, gallery) must:

1. **Work at every breakpoint** — No horizontal overflow, no overlapping text, no inaccessible elements at any viewport width from 320px to 1920px.

2. **Respect the spacing scale** — All margin, padding, and gap values come from the spacing token scale.

3. **Use the color token set** — No hard-coded color values. Every color references a `--color-*` token.

4. **Handle content variance** — Components must work with short and long text, missing optional fields, and varying image ratios (use `object-fit: cover` with defined aspect ratios).

5. **Include interaction states** — Hover, focus, active, and disabled states for all interactive elements. Focus states must be visible and use a ring or outline (not just color change).

---

## Performance contract

- First Contentful Paint: < 1.5s on 4G
- Largest Contentful Paint: < 2.5s
- Cumulative Layout Shift: < 0.1
- Total page weight (initial load): < 500KB
- No render-blocking resources beyond critical CSS
- Images lazy-loaded below the fold

---

## Delivery format

When generating code, deliver:

1. **Complete, runnable HTML** — Not fragments. Include `<!DOCTYPE html>`, `<head>` with meta tags and styles, and `<body>`.
2. **Embedded CSS** — In a `<style>` tag in `<head>`, unless the project uses an external stylesheet.
3. **No external dependencies** — Unless the project explicitly requires a framework. Default output is vanilla HTML + CSS.
4. **Commented sections** — Brief comments marking major sections (`<!-- Hero -->`, `<!-- Navigation -->`, etc.) but no over-documentation.
