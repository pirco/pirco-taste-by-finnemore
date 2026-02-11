# Corporate / Institutional Output Contract

Extends the foundation output contract. All foundation requirements apply. This document adds corporate-specific requirements. The foundation contract is never weakened — only extended.

---

## Navigation requirements

1. **Breadcrumb navigation on every page except the homepage.** Breadcrumbs appear as the first content element within `<main>`, above the page heading. Markup uses an ordered list within a `<nav aria-label="Breadcrumb">` element. Include `BreadcrumbList` structured data (JSON-LD).

```html
<nav aria-label="Breadcrumb" class="breadcrumb">
  <ol>
    <li><a href="/">Home</a></li>
    <li><a href="/academics">Academics</a></li>
    <li><a href="/academics/programs">Programs</a></li>
    <li aria-current="page">Computer Science</li>
  </ol>
</nav>
```

2. **Search accessible from every page.** Desktop: visible search input in the header or utility bar. Mobile: search accessible as the first element when the hamburger menu is opened. Search results pages include result count, query echo, and clear result items with title, excerpt, and content type.

3. **Skip navigation links.** First focusable element on every page: `<a href="#main-content" class="skip-link">Skip to main content</a>`. Visually hidden until focused. For sidebar layouts, include a second skip link to the sidebar.

---

## Content structure requirements

4. **Table of contents or section navigation for long content.** Content pages exceeding 1500 words or containing 4+ sections must include either a sticky table of contents (sidebar or inline) or anchor-linked section navigation at the top of the content. Each heading in the content corresponds to a TOC entry.

5. **Contact and department information is structured and machine-readable.** Department pages include a structured contact block with:
   - Department/office name
   - Physical address
   - Phone number (linked with `tel:`)
   - Email (linked with `mailto:`)
   - Office hours (if applicable)
   - Schema.org `Organization` or `ContactPoint` markup in JSON-LD

```html
<aside class="contact-block" aria-label="Department contact information">
  <h2>Contact</h2>
  <address>
    <p class="contact-name">Department of Computer Science</p>
    <p>Engineering Building, Room 300</p>
    <p>123 University Ave, Los Angeles, CA 90024</p>
    <p><a href="tel:+13105551234">(310) 555-1234</a></p>
    <p><a href="mailto:cs@university.edu">cs@university.edu</a></p>
    <p>Office hours: Mon–Fri, 9:00 AM – 5:00 PM</p>
  </address>
</aside>
```

---

## Form requirements

6. **Clear validation messages.** Inline validation errors appear adjacent to the field (not only at the top of the form). Error messages are specific: "Email address must include an @ symbol," not "Invalid input." Errors are associated with fields via `aria-describedby`.

7. **Field requirements are marked.** Required fields are indicated with both a visual marker and `aria-required="true"` (or the `required` attribute). A note at the top of the form states: "Fields marked with * are required."

8. **Multi-step forms include progress indicators.** Forms with more than one step display a progress bar or step indicator showing current position, total steps, and step labels. Users can navigate back to completed steps without losing data.

---

## Data display requirements

9. **Responsive data tables.** Tables that exceed the viewport width on mobile must implement one of two patterns:
   - **Horizontal scroll:** Table is wrapped in a container with `overflow-x: auto` and a visual scroll indicator (gradient or shadow on the right edge). The container has `role="region"`, `aria-label="Scrollable table"`, and `tabindex="0"` for keyboard scrolling.
   - **Card reflow:** Table rows convert to stacked card layouts on mobile, with each cell labeled by its column header.

10. **All interactive elements meet WCAG AAA contrast.** Buttons, links, form inputs, and navigation elements achieve 7:1 contrast ratio for text and 3:1 for non-text elements (borders, icons, focus rings) against their backgrounds. This extends foundation's AAA requirement from primary text to all interactive UI.

---

## Document and download requirements

11. **PDF and document links indicate file type and size.** Every link to a non-HTML resource includes the file type and approximate size in the link text or immediately adjacent:

```html
<a href="/reports/annual-2024.pdf">
  Annual Report 2024 <span class="file-meta">(PDF, 2.3 MB)</span>
</a>
```

File type icons are optional but must not be the sole indicator — text is always present.

---

## CSS token additions

Corporate projects extend the foundation `:root` token set:

```css
:root {
  /* Foundation tokens (all required) ... */

  /* Corporate additions */
  --color-bg-alt: #f1f3f5;           /* Alternating section background */
  --color-surface-raised: #ffffff;    /* Card/callout on alt background */
  --nav-height: 80px;                /* Header height */
  --nav-height-scrolled: 56px;       /* Reduced header on scroll */
  --sidebar-width: 33.333%;          /* Sidebar proportion */
  --content-width: 66.666%;          /* Content proportion */
  --max-width: 1200px;               /* Corporate max-width override */
}
```

---

## Performance contract additions

Foundation performance targets apply, plus:

- Total page weight for listing pages (directories, news, events): < 400KB initial load (before lazy-loaded images)
- Time to interactive for search: < 3s on 4G
- No layout shift from lazy-loaded sidebar content — reserve space with CSS

---

## Delivery format

Same as foundation (complete, runnable HTML with embedded CSS), with these additions:

- Breadcrumb markup included on all non-homepage pages
- JSON-LD structured data block in `<head>` for contact/organization pages
- Utility navigation bar above main header when audience selectors or login are present
- Mobile navigation includes full site tree, not an abbreviated version
