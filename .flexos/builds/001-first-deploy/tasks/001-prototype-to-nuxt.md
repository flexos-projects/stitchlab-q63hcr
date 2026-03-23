---
id: task-prototype-to-nuxt
title: "Convert Prototype to Nuxt Page"
type: build
subtype: task
status: pending
description: "Convert the prototype showcase page (index.html) into a Nuxt page component"
tags: [build, task, nuxt, prototype]
relatesTo: [builds/001-first-deploy/config.md, prototype/sitemap.md]
createdAt: "{{created_at}}"
---

# Convert Prototype to Nuxt Page

## What

Take `prototype/pages/index.html` and convert it into a Nuxt 4 page component at `app/pages/index.vue`.

## Steps

1. Scaffold the Nuxt project using the framework template
2. Migrate `prototype/shared/tokens.css` into the project's global CSS
3. Convert the HTML page into a Vue SFC with `<script setup lang="ts">`
4. Implement the theme toggle as a Vue composable
5. Wire up mock data as reactive state
6. Deploy to Vercel

## Acceptance Criteria

- [ ] `app/pages/index.vue` renders the same content as the prototype
- [ ] Theme toggle (light/dark) works with localStorage persistence
- [ ] Design tokens are loaded as CSS custom properties
- [ ] Page is responsive (mobile + desktop)
- [ ] Deployed and accessible at the project URL
