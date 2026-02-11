# Pirco Foundation Taste

Piroc Media's universal web design judgment. Every project inherits this.

## Philosophy

Typography is architecture — letterforms occupy space with structural intention. The interface disappears; visitors remember content, not chrome. Whitespace is material, not absence. Restraint is skill: every element justifies its existence. Performance is design (800ms > 4s regardless of polish). Accessibility is baseline, not feature. Design serves content, never competes with it.

## Constraints

**Typography:** Modular scale (16px base, 1.25 ratio, 12–60px range). Line-height: body 1.5–1.6, headings 1.05–1.15. Letter-spacing: body 0, display -0.02 to -0.04em. Max 2 font families. No font below 14px for body. No light weights below 20px.

**Spacing:** 8px base grid. Section gaps: 128–160px. Component gaps: 32–64px. Element gaps: 8–24px. All values on 4px sub-grid.

**Layout:** 12-column grid. Breakpoints: 640/768/1024/1280/1536. Prose max-width: 680px. Standard max-width: 1280px. Line length ≤75 characters.

**Color:** Token-based (bg, surface, text-primary/secondary/muted, border, border-subtle, accent/hover/muted). AAA contrast for primary text (7:1). No pure black/white. Max 5 active colors.

**Motion:** Micro 100–200ms, standard 250–350ms, dramatic 600–900ms. `prefers-reduced-motion` required. No infinite animations. No load-blocking animation. Parallax ≤0.1 rate, disabled on mobile.

**Images:** Consistent aspect ratios (16:9, 3:2, 1:1, 2:3). WebP + fallback. srcset required. Lazy loading below fold. Max 200KB standard, 400KB hero. Alt text required.

## Behavior

Start with content, then design. Remove before adding. Steal structure, not surface. Name every tradeoff. Prototype in the browser. Semantic HTML first. CSS custom properties for tokens. Mobile-first CSS. Progressive enhancement. No visual complexity to justify effort. No framework defaults without evaluation.

## Output Contract

Deliver complete, runnable HTML with embedded CSS. Design tokens in `:root`. Reduced-motion media query included. Mobile-first breakpoints. Every component works 320–1920px. All spacing from token scale. All colors from token set. Interaction states on all interactive elements. No external dependencies unless project requires them. Performance: LCP <2.5s, CLS <0.1, total weight <500KB.

## Examples Summary

**Good patterns:** Typography-driven heroes (no background images needed), 3-item navigation, 2-column project grids with subtle hover zoom, 4-level type hierarchy (meta/headline/lede/body), minimal footers (identity + nav + copyright), 3-field contact forms with visible labels.

**Bad patterns:** Gradient backgrounds competing with content, mega-menus, 4+ column grids with overlay hovers, self-congratulatory copy ("amazing", "world-class"), placeholder-only form labels, dark mega-footers with newsletter signups and social icon grids, pulse/bounce animations, scroll indicators.

---

*Full documentation: philosophy.md, constraints.md, behavior.md, output-contract.md, examples.md, context.md*
