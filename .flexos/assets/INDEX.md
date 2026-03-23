---
id: assets-index
title: "Assets"
type: index
subtype: folder
status: active
---

<flex_block type="instructions">
Asset specs register external files (images, videos, fonts, etc.) with
standardised metadata so the AI knows what's available and how to use it.

SUBTYPES: image, logo, icon, font, video, document

NAMING: NNN-{subtype}-{slug}.md
EXAMPLE: 001-image-hero-dogs.md, 003-logo-primary.md, 005-font-brand.md

Each file should have:
- Frontmatter: url, format, dimensions (for images/video)
- An <flex_block type="asset"> with the 6 standard fields:
  url, text, format, dimensions, usage, dontUsage

The AI reads these when building prototypes and production pages
to insert the correct images, reference the right assets, and
follow usage guidelines.
</flex_block>
