# Extracting Taste from a Reference Website

You are an LLM coding agent helping a developer build a website. The developer has given you a URL of a site they admire. Your job is to analyze that site and produce a structured taste document that captures its design judgment — not its content or branding, but the underlying decisions that make it feel the way it does.

## Process

### Step 1: Fetch and observe

Use your web browsing capabilities to visit the URL. Take screenshots if you can. Look at the page as a whole before examining details. Note your first impression in one sentence.

### Step 2: Analyze the six components

Work through each component systematically. For each, record concrete, specific observations — not vague impressions.

#### Philosophy (what does this site believe?)

Ask yourself:
- What does this site value most? (information density? atmosphere? minimalism? expression?)
- What is the relationship between content and design? (does design serve content, or is the design itself the content?)
- Who is the visitor, and how does the site treat them? (a guest? a reader? a shopper? a researcher?)
- What is absent that you'd expect to find? (the absences reveal philosophy more than the presences)

Write 3-5 belief statements in the form: "This site believes that..."

#### Constraints (what are the measurable parameters?)

Extract concrete values. Measure where possible, estimate where not:

**Typography:**
- What typefaces are used? How many families?
- What is the approximate body size? Heading sizes?
- What is the line-height on body text? On headings?
- Is there letter-spacing on headings? On uppercase text?
- What font weights are visible?

**Spacing:**
- What is the approximate gap between major sections?
- What is the gap between components (cards, content blocks)?
- What is the gap between elements within a component?
- Is the spacing generous, standard, or tight?

**Layout:**
- What is the approximate max-width of the content area?
- How many columns does the grid use for listing/grid content?
- Are layouts symmetric or asymmetric?
- What is the container padding?

**Color:**
- What is the background color? (sample it if possible)
- What is the text color?
- What is the accent color?
- How many total colors are in use?
- Is the palette warm, cool, or neutral?
- Is there a dark mode or dark sections?

**Motion:**
- Are there hover transitions? How fast do they feel? (instant, subtle, noticeable, slow)
- Are there scroll-triggered animations?
- Is there parallax?
- What is the overall motion personality? (none, restrained, playful, dramatic)

**Images:**
- What aspect ratios are used?
- Are images full-bleed or contained?
- Is there a consistent treatment (uniform sizes, mixed sizes, editorial arrangement)?
- What is the image style? (atmospheric, product-focused, editorial, informational)

#### Behavior (how does taste manifest in decisions?)

- How does the site handle navigation? (minimal, comprehensive, hidden until needed)
- How does the site handle calls to action? (aggressive, subtle, absent)
- How does the site prioritize content on the homepage? (hero image, text, product grid, editorial)
- How does the site handle mobile? (simplified, rearranged, or largely the same)
- What would a visitor notice first? Second? Third?

#### Output contract (what would the deliverables look like?)

Based on your analysis, write requirements that a developer would need to follow:
- What CSS custom properties would you define?
- What HTML patterns are recurring?
- What performance characteristics does the site seem to target?
- What accessibility patterns are visible?

#### Examples (positive and negative calibration)

Write one "good" example inspired by the reference site — a code snippet (HTML + CSS) for a key component (hero, card, or navigation) that captures the site's taste.

Write one "bad" example that shows what this site would *never* do — the anti-pattern of its design philosophy.

#### Context references

- The reference URL itself
- Any similar sites that share this aesthetic
- Any design movements or traditions this site belongs to

### Step 3: Determine the closest base package

Compare your analysis to the existing packages:

- **Foundation only** — if the site is minimalist and doesn't fit a specific domain
- **Foundation + Hospitality** — if the site is atmospheric, image-forward, warm, editorial
- **Foundation + Corporate** — if the site is information-dense, structured, accessible-first
- **Foundation + Artisan** — if the site is gallery-like, product-sacred, curated, generous whitespace

### Step 4: Write the client taste overrides

Produce the final output as a markdown block that the developer can paste into their project's `CLAUDE.md`:

```markdown
## Design Taste

Read and follow these taste packages for all design and front-end decisions.

Foundation: ~/GitHub/pirco/pirco-taste-by-finnemore/hospitality/TASTE.md
Domain:~/GitHub/pirco/pirco-taste-by-finnemore/[domain]/TASTE.md

For detailed constraints, behavior, and examples, fetch the full files:
~/GitHub/pirco/pirco-taste-by-finnemore/[domain]/constraints.md
~/GitHub/pirco/pirco-taste-by-finnemore/[domain]/examples.md

### Reference site
[URL] — [one-sentence description of what makes this site distinctive]

### Client overrides
[List specific values that diverge from the base + domain package]

### Client philosophy (append to domain philosophy)
[Any beliefs specific to this project that aren't captured by the domain package]

### Client constraints (override domain constraints)
[Specific typography, spacing, color, motion, or layout values]

### Client behavior notes
[Any behavioral patterns specific to this project]
```

## Important notes

- **Extract structure, not surface.** The goal is to capture the underlying decisions (spacing rhythm, type hierarchy, color restraint), not to copy the specific fonts, colors, or content of the reference site.
- **Be specific.** "Clean and minimal" is not useful. "16px body, 1.6 line-height, 680px max-width, 128px section spacing, 2-color palette (off-white + near-black)" is useful.
- **Name the tradeoffs.** If the reference site sacrifices information density for atmosphere, say so. If it sacrifices visual richness for speed, say so. These tradeoffs are the core of taste.
- **The base packages do the heavy lifting.** The client overrides should be short — 5-15 specific values. If the overrides are longer than a page, the wrong base package was chosen.
