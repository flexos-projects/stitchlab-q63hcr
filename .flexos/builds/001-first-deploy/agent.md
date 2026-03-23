---
id: build-001-agent
title: "Build Agent Instructions"
description: "AI agent execution instructions for the first deploy"
type: build
subtype: agent
status: draft
sequence: 2
tags: [build, agent, ai]
relatesTo: [builds/001-first-deploy/config.md]
createdAt: "{{created_at}}"
---

# Build Agent Instructions

Instructions for the AI agent executing this build.

## Context Loading

Before starting, the agent must read:

1. `builds/001-first-deploy/config.md` — stack and constraints
2. `design/001-tokens-design-system.md` — design tokens
3. `prototype/pages/index.html` — the source to convert
4. `prototype/shared/tokens.css` — CSS to migrate

## Task

Convert `prototype/pages/index.html` into a Nuxt page component. The resulting page should:

- Render identically to the prototype
- Use the same design tokens as CSS custom properties
- Support light/dark theme toggle
- Be deployed to Vercel

## Quality Gates

Before marking complete:

- [ ] Page renders correctly on mobile (375px) and desktop (1280px)
- [ ] Theme toggle works (light/dark)
- [ ] Design tokens match prototype values
- [ ] TypeScript compiles without errors
