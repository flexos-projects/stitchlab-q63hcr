---
id: design-index
title: "Design Specs"
type: index
subtype: folder
status: active
---

<flex_block type="instructions">
Design specs define HOW THINGS LOOK. Three levels:

SUBTYPES:
- tokens: Concrete values — colors, fonts, spacing, shadows, radii, transitions.
  Use <flex_block type="tokens"> with category and key-value pairs.
  These are the CSS custom properties that drive the entire visual system.
- patterns: CSS rules for components and layouts — how tokens are applied.
  Prose + code blocks showing class patterns, not individual values.
  e.g., "Cards use --radius-lg, --shadow-md, --space-lg padding"
- reference: Brand guidelines, mood boards, visual inspiration.
  External references that inform the tokens and patterns.

NAMING: NNN-{subtype}-{slug}.md
EXAMPLE: 001-tokens-brand-palette.md, 003-patterns-navigation.md, 005-reference-brand-guide.md

The blank project ships with a design-system.md that has initial tokens
derived from the project's theme color. This evolves as the project grows.
</flex_block>
