# Hospitality Constraints

> Inherits all foundation constraints. This document specifies ONLY the values that diverge. If a constraint is not listed here, the foundation value applies unchanged.

---

## Typography — divergences

**Scale extension:**
- Display headings may extend to 72px (`text-6xl: 72px`), beyond the foundation ceiling of 60px
- This larger size is reserved for hero headlines and single editorial moments — not general headings

**Font families:**
- A serif display font is **encouraged** for headings and editorial moments (foundation treats serif as optional)
- Body text remains sans-serif — the serif is for atmosphere, not reading
- Suggested pairings: serif display (e.g., Playfair Display, Cormorant, Libre Baskerville, Freight Display) with clean sans-serif body (e.g., Inter, DM Sans, Work Sans)
- The serif should have enough contrast and personality to evoke print editorial quality without feeling antiquated

**Letter spacing — serif headings:**
- Serif display headings: -0.01em to -0.03em (slightly less tight than sans-serif display, as serifs need more optical space)
- Serif italic, when used for pull-quotes or captions: 0 to 0.01em

**Weight:**
- Serif display headings may use weight 400–600 (lighter weights feel more editorial; heavy serifs feel dated)
- Italic is permitted for accent moments: pull-quotes, captions, location names

---

## Spacing — divergences

**Section spacing:** 160–200px (foundation: 128–160px)
- Hospitality layouts need more vertical breathing room between sections to maintain an unhurried pace
- Extended scale value: `space-48: 192px` and `space-50: 200px`

**Component gaps:** 48–80px (foundation: 32–64px)
- Image groups and content blocks benefit from wider separation in editorial layouts

**Element gaps:** unchanged from foundation (8–24px)

---

## Layout — divergences

**Asymmetric layouts:**
- Staggered and asymmetric image grids are encouraged (foundation defaults to symmetric grids)
- Images may be placed at different vertical offsets within a row to create editorial rhythm
- Odd-numbered image groups (3, 5) are preferred over uniform even grids

**Edge-to-edge imagery:**
- Full-bleed images are common, not exceptional (foundation treats full-bleed as "used sparingly")
- Hero sections typically span the full viewport width
- Alternating between contained and full-bleed sections creates a breathing rhythm

**Content max-width:**
- Standard layout: 1440px (foundation: 1280px) — wider canvas accommodates cinematic image layouts
- Prose max-width remains 680px

---

## Color — divergences

**Warm palette bias:**
- Foundation is temperature-neutral; hospitality skews warm
- Backgrounds: warm off-whites — `#faf8f5`, `#f5f0eb`, `#f8f4ef` (instead of neutral `#fafafa` or `#f8f7f4`)
- Dark tones: warm near-blacks — `#1a1512`, `#2c2420`, `#231f1b` (instead of neutral `#1a1a1a`)
- Text secondary: warm grays — `#6b5e54`, `#7a6e64`
- Text muted: `#a09489`, `#998c80`
- Border: `#d4c9be`, `#e0d6cc`

**Accent palette:**
- Gold and copper tones are permitted as accent colors: `#b8953f`, `#c9a84c`, `#a67c52`
- These replace the default blue accent from foundation
- Accent must still meet 4.5:1 contrast on the warm background

**Supporting earth tones:**
- Muted earth tones for tags, badges, and secondary UI: sage `#8a9a7c`, clay `#c4816e`, sand `#d4b896`, stone `#9c9488`
- Maximum 5 active colors rule still applies — choose judiciously

**Dark sections:**
- Hospitality sites often use dark sections (warm dark backgrounds with light text) for atmosphere
- When using dark sections, define a parallel token set: `--color-dark-bg`, `--color-dark-text`, etc.
- Dark section backgrounds: `#1a1512`, `#2c2420`
- Dark section text: `#f5f0eb`, `#e8e0d8`

---

## Motion — divergences

**Duration ranges:**
- Micro-interactions: 150–250ms (foundation: 100–200ms) — slightly softer transitions
- Standard transitions: 400–600ms (foundation: 250–350ms) — noticeably slower, creating an unhurried feel
- Dramatic transitions: 800–1200ms (foundation: 600–900ms) — cinematic pace for hero and gallery

**Parallax:**
- Permitted at 0.05–0.15 rate (foundation caps at 0.1)
- Used on hero images and section backgrounds — not on text or UI elements
- Still disabled on mobile and when `prefers-reduced-motion` is active

**Hospitality-specific animations:**
- **Image reveals:** Images may animate in using `clip-path` (wipe reveal) or opacity + subtle translate. Duration 600–900ms. Triggered once on scroll-enter.
- **Ken Burns effect:** Permitted on hero images only. Very subtle — scale from 1.0 to 1.05 over 15–20 seconds. Creates a living, breathing quality. Disabled when reduced motion is preferred.
- **Text fade-up:** Headings and key text may fade in with a 20–30px upward translate. Duration 500–700ms, staggered by 100ms per element. Maximum 3–4 elements in sequence.

**Easing — hospitality preference:**
- Prefer softer curves: `cubic-bezier(0.25, 0.1, 0.25, 1)` for standard transitions
- Enter: `cubic-bezier(0.0, 0.0, 0.2, 1)` (decelerate, as foundation)
- Exit: `cubic-bezier(0.4, 0.0, 0.6, 1)` (gentler exit than foundation's accelerate-out)

---

## Images — divergences

**Hero aspect ratio:**
- 21:9 is the default hero ratio (foundation offers 16:9 or 21:9 as options)
- This cinematic ratio creates a widescreen impression that evokes the property's sense of space
- On mobile, hero may shift to 3:2 or 16:9 to maintain usable image height

**Editorial image grids:**
- Mixed aspect ratios within a single grid are encouraged: 3:2 alongside 2:3 alongside 16:9
- This asymmetry creates the editorial, magazine-like quality that distinguishes hospitality from corporate
- Foundation's "consistent aspect ratios within a project" rule is relaxed for editorial grid sections

**Full-bleed frequency:**
- Full-bleed images are standard, not exceptional
- At least one full-bleed image per major content section is typical

**Quality ceiling:**
- Standard images: 300KB (foundation: 200KB) — hospitality photography demands higher fidelity
- Hero images: 500KB (foundation: 400KB)
- The increased weight is justified by the centrality of imagery to the hospitality experience
- Compression should still be aggressive — the ceiling is higher, not the default

**Photography direction (when advising on image selection):**
- Natural light preferred over studio lighting
- Spaces should feel inhabited but not crowded — one or two people, not a staged group
- Show the experience, not the facility: a coffee cup on the balcony railing at sunrise, not a wide shot of the lobby
- Time of day matters: golden hour, blue hour, and candlelight create more atmosphere than midday flat light
