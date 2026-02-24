## Design Taste — Replica

### Step 1: Extract taste from the reference site
Use WebFetch to load https://claude-taste.piroc.com/extract.md and follow
its process against the reference site below. Save the resulting taste
document to this repo as `taste-extract.md` before writing any code.

Reference: https://flatvernacular.com

### Step 2: Load the base taste packages
Use WebFetch to load these URLs and follow them for all design decisions:

Foundation: https://claude-taste.piroc.com/foundation/TASTE.md
Domain: https://claude-taste.piroc.com/artisan/TASTE.md

For detailed guidance, also fetch:
- https://claude-taste.piroc.com/artisan/constraints.md
- https://claude-taste.piroc.com/artisan/examples.md

### Step 3: Apply client overrides

#### Fidelity standard
This is a **replica project**. The reference site is the spec.
- Match typography, spacing, color, layout, and motion exactly
- Use browser DevTools values from the reference site, not taste package defaults
- Where taste packages and the reference site conflict, the reference site wins
- Document every intentional deviation and why it was necessary

#### Content and data preservation
- All existing Shopify sections, blocks, and settings schemas must work as-is
- All metafield references must be preserved with identical keys
- All image references and asset URLs must remain functional
- The store owner must be able to switch to this theme without re-entering content

#### What "pixel-perfect" means
- Measure the reference site at 1440px, 768px, and 375px breakpoints
- Match font sizes, weights, line-heights, and letter-spacing to measured values
- Match section spacing, component gaps, and padding to measured values
- Match colors by sampling — do not approximate
- Match hover states, transitions, and animation timing
- Flag anything you cannot replicate due to platform constraints

#### Architecture
- Base theme: Shopify Dawn (latest)
- Minimize changes to Dawn's core files — prefer section/snippet overrides
- Keep Dawn's existing CSS architecture; add custom styles in a separate file
- Preserve Dawn's accessibility features and semantic HTML

### Notes
This is a Shopify theme managed via GitHub. Commit working increments often.
