# Corporate / Institutional Behavior

How corporate taste manifests in day-to-day design and development decisions. Inherits foundation behavior — this document covers corporate-specific patterns.

---

## Decision-making process

1. **Information architecture precedes visual design.** Before any color, layout, or component decision, the complete site structure must be mapped: page hierarchy, navigation paths, content types, audience flows. A university or enterprise site lives or dies by its IA. No amount of visual design fixes a confusing structure.

2. **Every page answers two questions within 3 seconds.** "What is this?" and "What can I do here?" If a visitor lands on a department page, the department name, a one-sentence description, and the primary actions (contact, apply, learn more) must be visible without scrolling. If they cannot orient themselves in 3 seconds, the page has failed.

3. **Navigation is explicit — never hide important paths.** Foundation's taste for minimal navigation (3 links) does not scale to institutional complexity. Corporate sites must make all major paths visible and discoverable. Hiding navigation behind progressive disclosure (dropdowns, accordions, "more" links) is acceptable for secondary paths, never for primary ones.

4. **Tables, lists, and structured data are first-class elements.** In foundation, the primary content types are prose, images, and cards. Corporate adds: data tables, definition lists, specification lists, directory grids, and timeline/event listings. These are not afterthoughts or edge cases — they are core content patterns that deserve dedicated styling and responsive behavior.

5. **Search is prominent.** On sites with more than 20 pages, search is a primary navigation mechanism. It should be visible in the header (not hidden behind an icon on desktop) and accessible from every page. Search results must show clear titles, contextual excerpts, and content type labels.

---

## Tone of design decisions

- **Functional clarity over quiet confidence.** Foundation aims for design that "disappears." Corporate aims for design that *explains*. Labels are explicit. Headings are descriptive. Nothing relies on visual implication alone — if a sidebar contains related links, it is labeled "Related Links," not left to visual proximity to convey the relationship.

- **Consistency over craft.** Every department page should look structurally identical. Every listing page should use the same grid. Every contact block should follow the same pattern. In corporate taste, the system is the design. Individual page craft is subordinate to system-wide consistency.

- **Content is chunked for scanning.** Long paragraphs are broken into shorter ones. Key information is extracted into callout boxes, key-fact sidebars, or summary lists at the top of the page. Headers are frequent and descriptive — they serve as anchor points for scanning, not as literary devices.

- **No ambiguity in labels or actions.** Button labels say exactly what they do: "Apply to this program," "Download the PDF (2.3 MB)," "Contact the admissions office." Never "Learn More," "Click Here," or "Get Started." Link text is self-describing — it makes sense out of context (critical for screen reader users navigating by links).

---

## Technical behavior

- **Breadcrumb component is mandatory.** Every page template below the homepage includes a breadcrumb trail as the first element within `<main>`. Breadcrumbs use structured data markup (`BreadcrumbList` schema) for SEO and accessibility.

- **Skip navigation links.** A "Skip to main content" link is the first focusable element on every page. For pages with sidebars, add "Skip to sidebar" as well.

- **Structured data for contact information.** Department pages, people profiles, and location pages include schema.org markup (`Organization`, `Person`, `LocalBusiness`, `ContactPoint`) so that information is machine-readable and appears correctly in search results.

- **Table responsiveness is required.** Data tables on mobile must either horizontally scroll within a container (with a visual indicator that scrolling is possible) or reflow into a card/list layout. Tables must never cause the page to scroll horizontally.

- **Document links are annotated.** Links to PDFs, Word documents, or other non-HTML files must indicate the file type and size: "Annual Report 2024 (PDF, 2.3 MB)". This is an accessibility and usability requirement.

---

## What we don't do (in addition to foundation's list)

- Use hero images as the primary visual element on informational pages
- Hide contact information below the fold
- Use carousel/slider components for anything other than image galleries
- Rely on icons without text labels for primary navigation
- Build pages that require JavaScript for basic content access
- Use infinite scroll on listing pages (always provide pagination)
- Create "landing page" layouts for internal content pages
- Let visual novelty override navigational consistency across sections
