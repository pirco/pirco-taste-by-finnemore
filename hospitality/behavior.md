# Hospitality Behavior

> Inherits foundation behavior. This document describes how hospitality taste manifests in day-to-day design and development decisions beyond the foundation defaults.

---

## Image selection is a design decision

In foundation projects, images support the content. In hospitality projects, images ARE the content. Choosing the right photograph is as important as choosing the right layout. Before building any section, the image selection must be finalized or at minimum understood — because the image determines the composition, the color temperature of the section, and the emotional register of the surrounding typography.

When selecting or recommending images:
- A single extraordinary photograph outperforms three good ones
- Crop with intention — the same image at 21:9 and 3:2 tells different stories
- Consistency of light and color temperature across a page matters more than individual image quality
- If the photography is weak, no amount of layout sophistication will save the section

---

## Atmosphere first, information second

The sequencing of content on a hospitality page differs from a standard informational site. The foundation behavior of "start with content" still applies, but the emotional arc is:

1. **Feel** — The guest encounters atmosphere (full-bleed image, restrained headline, sense of place)
2. **Orient** — The guest understands where they are (property name, location, navigation)
3. **Explore** — The guest discovers details (rooms, dining, experiences)
4. **Act** — The guest is ready to book or inquire (reservation CTA, contact)

This sequence means the hero section should never lead with a rate, a promotion, or a bullet list of amenities. It should lead with a feeling.

---

## Let photographs do the emotional work

When a section has a strong photograph, reduce every other element to its minimum:
- Headline: short, even a single word ("Arrive", "Dine", "Rest")
- Body text: one or two sentences maximum — atmospheric, not descriptive
- CTA: a quiet text link, not a button
- The photograph is doing the selling; the text is providing the caption

When photography is unavailable or weak, typography and spacing must compensate. A serif headline at generous scale with warm color and ample whitespace can create atmosphere without imagery — but this is the fallback, not the default.

---

## Typography should feel considered, not loud

In hospitality, the serif display font is a privilege, not a default. Use it for:
- The main hero headline
- Section titles that introduce a new area of the property
- Pull-quotes from reviews or editorial content
- Occasionally, a single word used at large scale for dramatic effect

Do NOT use the serif for:
- Navigation
- Buttons or CTAs
- Form labels
- Metadata (dates, prices, room details)
- Body paragraphs

The serif creates editorial contrast. If everything is in the serif, nothing is.

---

## Navigation should be invisible until needed

Hospitality navigation should recede further than the foundation default. Options:
- Transparent header over the hero image, transitioning to solid on scroll
- A minimal word-mark (not a full logo lockup) with 3–5 links
- On immersive pages, consider hiding navigation entirely until the guest scrolls
- Mobile navigation: a simple slide-in panel, not a full-screen takeover

The booking/reservation action should be accessible from the header but should NOT visually dominate. A text link saying "Reserve" or "Book a Stay" in the nav is better than a contrasting button.

---

## Booking and CTAs: present but never aggressive

The primary conversion action in hospitality is the reservation. It must be:
- **Accessible** — present on every page, reachable without hunting
- **Refined** — styled as a natural part of the design, not a bolt-on conversion element
- **Patient** — it does not pulse, glow, follow the scroll, or change color to attract attention

Good CTA patterns for hospitality:
- A quiet link in the header: "Reserve" in the same type style as other nav items
- A section at natural scroll points: "Plan your stay" with a date picker or link to the booking page
- An inline prompt after editorial content: "For reservations, contact [phone] or reserve online"

Bad CTA patterns:
- Sticky bottom bars with "BOOK NOW"
- Pop-ups after 5 seconds on the page
- Animated buttons in contrasting colors
- Multiple competing CTAs on the same viewport

---

## Seasons and time of day can influence the visual story

The best hospitality sites acknowledge that a property is not a static product. Consider:
- Photography that spans seasons — a hero image gallery (not a carousel with dots, but a slow crossfade or curated selection) showing the property in different light
- Seasonal content blocks: "Winter at [Property]" with appropriate photography
- Time-of-day awareness in photography selection: evening interiors for the restaurant, morning light for the rooms, golden hour for the exteriors
- If implementing dynamic content: subtle shifts in the hero image based on the visitor's local time (evening visitors see evening imagery) — but only if the photography supports it

---

## What hospitality taste does NOT do

- Use stock photography of people shaking hands or pointing at laptops
- Present rooms as product listings with feature checkboxes
- Reduce a dining experience to a menu PDF link
- Use promotional language ("Limited time offer!", "Best rate guaranteed!")
- Auto-play video with sound
- Use image carousels with dot indicators and arrow buttons
- Stack amenity icons in a grid (the hotel gym icon grid is a cliche to avoid)
- Place a booking widget that dominates the hero section
