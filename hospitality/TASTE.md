# Pirco Hospitality Taste

Inherits from foundation. This package extends the universal Piroc taste for hotels, resorts, and luxury venues. Only divergences from foundation are documented here — all foundation constraints, behaviors, and contracts remain in effect.

## Philosophy

The visitor is a guest, not a user. The site is the lobby — atmosphere must be felt before information is delivered. Images carry the emotional story; layout and typography exist to give them room. Restraint is luxury: one image instead of twelve, one sentence instead of a paragraph, silence instead of a sales pitch. Time moves differently on a hospitality site — the guest is in a state of anticipation, not productivity. Every page is a distinct room within a unified aesthetic.

## Constraints (divergences from foundation)

**Typography:** Serif display font encouraged for headings and editorial moments (body stays sans-serif). Display headings extend to 72px. Serif weights 400–600; italic permitted for pull-quotes, captions, location names.

**Spacing:** Section gaps 160–200px (foundation: 128–160px). Component gaps 48–80px (foundation: 32–64px). The pace is unhurried.

**Layout:** Asymmetric editorial grids encouraged. Staggered image placement with mixed sizes. Full-bleed imagery is standard, not exceptional. Content max-width extends to 1440px for cinematic image layouts.

**Color:** Warm palette bias. Backgrounds: warm off-whites (`#faf8f5`, `#f5f0eb`). Darks: warm near-blacks (`#1a1512`, `#2c2420`). Gold/copper accents permitted (`#b8953f`, `#a67c52`). Earth tone supporting colors. Dark atmospheric sections with parallel token sets.

**Motion:** Slower standard transitions (400–600ms vs. 250–350ms). Parallax at 0.05–0.15 rate. Image reveal animations (clip-path, opacity) at 600–900ms. Ken Burns on hero images (scale to 1.05 over 15–20s). Text fade-up with staggered timing. All still respect `prefers-reduced-motion`.

**Images:** 21:9 hero ratio (default, not optional). Mixed aspect ratios in editorial grids (3:2, 2:3, 16:9 together). Higher quality ceiling: 300KB standard, 500KB hero. Natural light, inhabited spaces, golden hour preferred.

## Behavior

Image selection is as important as layout — a single extraordinary photo outperforms three good ones. Sequence content as feel-orient-explore-act: atmosphere first, then wayfinding, then details, then booking. Let photographs do the emotional work; reduce surrounding text to its minimum. Typography choices use serif sparingly for editorial contrast — if everything is in serif, nothing is. Navigation recedes further than foundation default (transparent header, minimal word-mark, 4–6 links). Booking CTAs are present on every page but styled as refined text links, never pulsing buttons or sticky bars. Seasons and time of day inform photography selection.

## Output Contract (extensions)

Hero: full-viewport cinematic image, 21:9 desktop, minimal text overlay, Ken Burns permitted, no carousel. Image grids: asymmetric/editorial layouts with mixed ratios and generous gaps, not uniform thumbnails. Rooms: each room is a narrative (atmospheric lead image, serif display name, story-like sequencing, specs as quiet metadata, rate understated, single refined reservation link). Galleries: curated editorial sequences with varied image sizes, not thumbnail grids. Navigation: may be transparent over hero, "Reserve" as text link not button. Dark sections: use parallel warm dark token set. Warm palette tokens required in `:root`. Performance: page weight ceiling 800KB, LCP < 3.0s (hero image accommodation). Serif `@font-face` with `font-display: swap`.

## Examples Summary

**Good patterns:** Cinematic full-viewport hero with serif property name and quiet tagline over gradient; room pages as editorial narratives with atmospheric photography, story-like sequencing, and specifications as metadata; restaurant sections with single beautiful image, serif name, two-sentence atmospheric description; editorial galleries with varied image sizes, asymmetric grid, generous whitespace, and curated sequencing.

**Bad patterns:** Hero carousels with dots/arrows and "BOOK NOW" pulsing button with overlaid booking widget; room pages as product listings with icon feature grids, strikethrough pricing, and urgency text; amenity sections as emoji icon card grids with generic descriptions; uniform thumbnail galleries with filter tabs, lightbox onclick handlers, and "Load More" pagination.

## Context

Benchmarks: Aman Resorts (atmosphere-first presentation), The Standard Hotels (editorial approach), Singita (image sequencing), Cereal Magazine and Kinfolk (lifestyle editorial register). Anti-patterns: booking platform density tactics, template hotel themes with every hospitality cliche. Typography: Freight Display, Cormorant, Playfair Display paired with clean sans-serifs. Piroc's Wynn Hotels work and Berlin typographic tradition inform the restraint-as-luxury principle.

---

*Full documentation: philosophy.md, constraints.md, behavior.md, output-contract.md, examples.md, context.md*
