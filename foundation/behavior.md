# Foundation Behavior

How Piroc's taste is expressed in day-to-day design and development decisions.

---

## Decision-making process

1. **Start with content.** Before any layout, color, or component decision, understand what the visitor needs to read, see, or do. Design follows content structure, never the reverse.

2. **Remove before adding.** When a design feels incomplete, the instinct is to add elements. Resist. First ask what can be removed. The answer is almost always "more than you think."

3. **Steal the structure, not the surface.** Reference sites are studied for their underlying decisions — grid logic, type hierarchy, spacing rhythm, content sequencing — not their colors, fonts, or visual details.

4. **Name the tradeoff.** Every design choice has a cost. When choosing larger type, acknowledge the reduced content density. When choosing a sparse layout, acknowledge the increased scroll depth. Make tradeoffs explicit.

5. **Prototype in the browser.** Static mockups hide the most important qualities: load time, scroll behavior, responsive reflow, hover states, keyboard navigation. Get to HTML/CSS early.

---

## Tone of design decisions

- **Quiet confidence over visual loudness.** A Piroc site doesn't shout. It presents with clarity and lets the content carry the weight.

- **Precision over decoration.** Alignment, consistent spacing, and typographic hierarchy do more visual work than gradients, shadows, or illustrations.

- **Functional beauty.** If something looks good but doesn't serve the user, it's not good design. If something serves the user but looks bad, the execution isn't finished yet.

- **Editorial sensibility.** Treat the page like a well-designed publication: clear hierarchy, deliberate pacing, considered breaks between sections.

---

## Technical behavior

- **Semantic HTML first.** Use the correct element for its purpose. `<nav>`, `<main>`, `<article>`, `<section>`, `<aside>`, `<figure>`. Div soup is a code smell.

- **CSS custom properties for design tokens.** Colors, spacing, typography values live in custom properties. Components consume tokens, never hard-coded values.

- **Mobile-first CSS.** Base styles target the smallest viewport. Media queries add complexity for larger screens, never the reverse.

- **Progressive enhancement.** Core content and functionality work without JavaScript. JS enhances — it doesn't gate access.

- **System fonts as default.** Only load custom fonts when they serve a clear design purpose. Every font file is a performance cost that must be justified.

---

## What we don't do

- Add visual complexity to justify design effort
- Use framework defaults without evaluating them against project taste
- Implement features because a template includes them
- Prioritize visual novelty over usability
- Copy trends without understanding the underlying design logic
- Ship without testing on real devices at real network speeds
