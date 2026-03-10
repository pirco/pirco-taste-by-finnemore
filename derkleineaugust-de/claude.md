## Design Taste — Replica

### Step 1: Extract taste from the reference site
Use WebFetch to load https://claude-taste.piroc.com/extract.md and follow
its process against the reference site below. Save the resulting taste
document to this repo as `taste-extract.md` before writing any code.

Reference: https://derkleineaugust.de

### Step 2: Load the base taste packages
Use WebFetch to load these URLs and follow them for all design decisions:

Foundation: https://claude-taste.piroc.com/foundation/TASTE.md
Domain: https://claude-taste.piroc.com/artisan/TASTE.md

For detailed guidance, also fetch:
- https://claude-taste.piroc.com/artisan/constraints.md
- https://claude-taste.piroc.com/artisan/examples.md

### Step 3: Apply client overrides

#### Fidelity standard
We need a **fresh website** for derkleineaugust.de. the current site has been been built as a sister theme on a multisite WP installation for claerchensball.haus and is very much based on that design. we want something more elegant, french, light and simple. yet ELEGANT.

#### Content and data preservation
- We are building this new mini site with Kirby because there are only a few fields that need updating.

#### What 'elegant, french, light and simple' means
- The design should be airy, light and simple. Big, yet light typography, not afraid to land on top of images. things scroll smoothly, at different speeds, providing a parallax effect. maybe even slightly off the perfect vertical path. but sliding away like a butterfly to the side of the screen. you can add little decorative vignettes. like, turn the A of "der kleine August" into a single letter vignette!

#### Architecture
- simple does it here. using Kirby CMS. 

### Notes
This site will be hosted on Siteground and the files will be hosted as a repository on github.com. we git pull via ssh from the server. 