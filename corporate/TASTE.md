# Pirco Corporate / Institutional Taste

Inherits from foundation. This package extends Piroc's universal taste for institutions, enterprises, and science organizations — sites where information clarity is the primary design objective. Based on Piroc's work with UCLA, USC, Amgen, and Disney.

**Load this file into project CLAUDE.md. For full documentation, see the individual files: philosophy.md, constraints.md, behavior.md, output-contract.md, examples.md, context.md.**

## Philosophy

Information clarity above atmosphere. The visitor is task-oriented — they came to find something specific. Every design decision is measured against speed of retrieval. Credibility comes from clarity, not visual flourish. Complex organizations need explicit wayfinding: breadcrumbs, section navigation, clear labeling. Trust is built through consistent, predictable page structures across every department and section. Accessibility is elevated from baseline to primary concern — WCAG AAA is the target.

## Constraints (divergences from foundation)

**Typography:** Sans-serif only. No display serifs. Base may be 15px for density. Weight range 400–600 (no 700). Liberal use of text-sm/text-xs for metadata and labels.

**Spacing:** Tighter. Section spacing 96–128px (foundation: 128–160). Component gaps 24–48px (foundation: 32–64). Denser layouts are acceptable.

**Layout:** Max-width 1200px (foundation: 1280). Sidebar layouts are standard: content 2/3, sidebar 1/3 within 1200px. Breadcrumbs required on all pages below homepage. Full-width background colors permitted for section separation.

**Color:** Cool/neutral palette. Off-whites: #f8f9fa, #f1f3f5. Blues and cool grays for accent. No warm tones unless brand-mandated. WCAG AAA (7:1) for ALL text including secondary (foundation allows 4.5:1 for secondary).

**Motion:** Micro-interactions only, 100–200ms. No parallax. No scroll-triggered animations. No hero animations. Instant state changes with subtle easing. Foundation's standard and dramatic duration tiers are eliminated.

**Images:** Informational only — headshots, facility photos, charts, diagrams. Standard ratios: 16:9, 4:3, 1:1. No full-bleed heroes. Max 150KB per image (foundation: 200KB).

**Navigation:** Mega-menu supported for complex site structures. Utility nav bar (search, login, language) above main header. Sticky header reduces height on scroll. Mobile: hamburger with full navigation tree.

## Behavior

Information architecture precedes visual design. Every page answers "what is this?" and "what can I do here?" within 3 seconds. Navigation is explicit — never hide important paths. Tables, lists, and structured data are first-class content types. Search is prominent and accessible from every page. Content is chunked for scanning: frequent headings, lists over paragraphs, callout boxes for key facts. No ambiguity in labels or actions — "Apply to this program" not "Learn More." Document links indicate file type and size.

## Output Contract (extends foundation)

- Breadcrumb navigation on every page except homepage (with BreadcrumbList structured data)
- Search accessible from every page
- Table of contents for long content (1500+ words or 4+ sections)
- Contact/department info structured and machine-readable (schema.org JSON-LD)
- Forms: inline validation, marked required fields, progress indicators for multi-step
- Data tables responsive: horizontal scroll or card reflow on mobile
- All interactive elements meet WCAG AAA contrast (7:1 text, 3:1 non-text)
- PDF/document links show file type and size
- Additional tokens: --color-bg-alt, --nav-height, --nav-height-scrolled, --sidebar-width, --content-width, --max-width: 1200px

## Examples Summary

**Good patterns:** Department landing pages with clear heading, brief description, structured link sections, contact sidebar. Program pages with key-facts block, table of contents, scannable requirements lists. Faculty directories as filterable grids with name/title/area. News listings as chronological lists with date, title, excerpt, category tag, and pagination.

**Bad patterns:** Hero banners with stock photos on informational pages. Vague mission statements and marketing copy where structured links should be. Carousels for content that should be visible at once. Faculty pages as single-person slideshows with lengthy bios. News grids with large images, hidden dates, and infinite scroll. "Learn More" and "Read More" as link text. Promotional language ("world-class," "cutting-edge") substituting for factual content.

---

*Reference sites: MIT, ETH Zurich, GOV.UK, U.S. Web Design System. Full context: context.md*
