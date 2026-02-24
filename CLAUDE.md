# Taste

A library of encoded design judgment for web development. This is not a component library — it contains no reusable code. It is structured documentation of web design decisions that LLM coding agents (like Claude Code) use to produce consistently high-quality, opinionated output.

## How Taste Packages Work

Each package encodes judgment using six components:

| Component | Purpose | Inheritance |
|---|---|---|
| **Philosophy** | Core beliefs that constrain choices | Concatenates (child appends to parent) |
| **Constraints** | Named parameters with allowed values | Deep merges (child overrides matching keys) |
| **Behavior** | How taste is expressed in decisions | Concatenates |
| **Output Contract** | Required shape of deliverables | Child overrides parent entirely |
| **Examples** | Positive AND negative calibration pairs | Child overrides parent entirely |
| **Context** | Pointers to related resources | Merges (union) |

Each package has a condensed `TASTE.md` (~1500 tokens) for quick loading and individual component files for full detail.

## Package Hierarchy

```
foundation/     <- Every project inherits this (typography, spacing, color, motion, layout)
├── hospitality/ <- Hotels, resorts, luxury venues (warm, image-forward, editorial)
├── corporate/   <- Institutions, enterprises, science (clarity-first, accessible, structured)
└── artisan/     <- Boutique brands, studios, e-commerce (gallery-like, product-sacred)
```

Override precedence: **client-specific > domain > foundation**

## Quick Reference

| Client Type | Packages |
|---|---|
| Hotel, resort, luxury venue | foundation + hospitality |
| Restaurant, bar, spa | foundation + hospitality |
| University, hospital, enterprise | foundation + corporate |
| Research institute, government | foundation + corporate |
| Boutique brand, artisan producer | foundation + artisan |
| Design studio, creative practice | foundation + artisan |
| Small e-commerce, maker shop | foundation + artisan |
| General / doesn't fit above | foundation only |

## Using in a Client Project

Add this to the client project's `CLAUDE.md`:

```markdown
## Design Taste

Read and follow these taste packages for all design and front-end decisions.

Use WebFetch to load the following URLs and follow them as your design system:

Foundation: https://claude-taste.piroc.com/foundation/TASTE.md
Domain: https://claude-taste.piroc.com/hospitality/TASTE.md

For detailed guidance on any component, fetch the full files in the package directory
(philosophy.md, constraints.md, behavior.md, output-contract.md, examples.md, context.md).

### Client Overrides
- Brand color: #1B4D3E
- Display typeface: Cormorant Garamond
- Hero aspect ratio: 21:9
```

### Override rules

1. Foundation taste applies to everything unless overridden
2. Domain package overrides foundation where they conflict
3. Client overrides (in the client's CLAUDE.md) override everything
4. When a domain or client specifies a constraint value, use it. When silent, fall back to foundation.
5. Philosophy and behavior accumulate — domain adds to foundation, never replaces it

## Reading the Packages

- Start with `TASTE.md` in the relevant package — it's the condensed summary
- When you need specifics (exact spacing values, code examples, detailed rationale), read the individual component files
- `examples.md` is the most powerful calibration tool — study the positive/negative pairs before generating any design code
- `constraints.md` contains the hard technical parameters — treat these as your design token reference

## Extracting Taste from Reference Sites

If a developer gives you a URL of a site they admire, fetch `/extract.md` for a structured process to analyze the site and produce a custom taste package from it.

## Contributing

To add a new domain package:

1. Create a directory at the root (e.g., `editorial/`)
2. Create all 7 files following the existing package structure
3. State "Inherits from foundation" at the top of each file
4. Document only divergences from foundation — don't repeat shared constraints
5. Include positive/negative example pairs specific to the domain
6. Add the domain to the quick reference table in this file
