---
id: prototype-sitemap
title: "Sitemap"
description: "Page hierarchy and routing structure for the prototype"
type: prototype
subtype: config
status: draft
sequence: 1
tags: [prototype, sitemap, pages, navigation]
relatesTo: [docs/003-pages.md, design/001-tokens-design-system.md]
createdAt: "{{created_at}}"
updatedAt: "{{created_at}}"
---

<flex_block type="instructions">
This file defines the prototype's page structure. The AI reads this to know
what pages exist, their hierarchy, and what each page should contain.

File layout:
- index.html — portal/showcase page (served at domain root)
- placeholder.html — "something's coming" page (served when rootMode=placeholder)
- pages/ — prototype screens (landing, dashboard, etc.)
- shared/ — tokens.css, components.css, mock-data.js/json

When generating new prototype pages, add them to the pages array below
then create the HTML file in prototype/pages/.
</flex_block>

# Sitemap

## Portal Pages

These are at the prototype root — not in pages/:

| File | Purpose | Served at |
|------|---------|-----------|
| `index.html` | Project showcase with design system preview | `/` (default) |
| `placeholder.html` | FlexOS branded "something's coming" | `/` (when rootMode=placeholder) |

## Prototype Pages

<flex_block type="config">
{
  "pages": [],
  "shared": {
    "tokens": "shared/tokens.css",
    "components": "shared/components.css",
    "mockData": "shared/mock-data.js",
    "mockDataJson": "shared/mock-data.json"
  }
}
</flex_block>

No prototype pages yet. Use the chat to generate them:
- "Generate a landing page prototype"
- "Create a dashboard prototype"

## Adding Pages

1. Add an entry to the pages array above
2. Create the HTML file in `prototype/pages/`
3. Link `../shared/tokens.css` and `../shared/components.css` in the `<head>`
4. Import mock data with `<script src="../shared/mock-data.js"></script>`
5. Use design tokens as CSS custom properties throughout

## Routing

Controlled by `deploy.rootMode` in project.json:

| rootMode | Domain root `/` serves |
|----------|----------------------|
| `placeholder` | placeholder.html |
| `prototype` / `portal` | index.html |
| `app` | Nuxt app (nuxt template only) |

Vercel rewrites in vercel.json handle the mapping.
