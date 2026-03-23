---
id: pages-index
title: "Page Specs"
type: index
subtype: folder
status: active
---

<flex_block type="instructions">
Page specs define WHAT APPEARS ON SCREEN.

SUBTYPES:
- route: A page with a URL. Has a `route` field (e.g., `/dogs/:id`).
- component: A reusable UI element used across multiple pages (e.g., navbar, dog card).
- layout: A page shell/wrapper that provides shared structure (e.g., app shell, auth layout).
- overlay: A modal, sheet, drawer, or dialog that appears on top of a page.

NAMING: NNN-{subtype}-{slug}.md
EXAMPLE: 001-route-landing.md, 005-component-navbar.md, 008-layout-app-shell.md

SPECIAL FIELDS:
- route: URL path (for route subtype only), e.g., `/dogs/:id`
- prototype: path to current prototype HTML, e.g., `prototype/landing-v2.html`

Each file should include:
- What the page shows (sections, content areas)
- What data each section needs (linked to database specs)
- Key interactions (linked to flow specs)
- SEO requirements (for routes)
- relatesTo: linked features, flows, database specs, design specs
</flex_block>
