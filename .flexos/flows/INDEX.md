---
id: flows-index
title: "Flow Specs"
type: index
subtype: folder
status: active
---

<flex_block type="instructions">
Flow specs define HOW THINGS HAPPEN step by step.

SUBTYPES:
- user: User-facing journeys (e.g., adoption application, onboarding)
- auth: Authentication and authorization flows (e.g., login, signup, OAuth)
- backend: Server-side processes (e.g., email notifications, data sync)

NAMING: NNN-{subtype}-{slug}.md
EXAMPLE: 001-user-adoption-journey.md, 003-auth-google-login.md

Each file should include:
- Trigger: what starts this flow
- Steps: ordered sequence of actions and decisions
- Error paths: what happens when things go wrong
- A <flex_block type="flow"> with the step-by-step JSON for visual rendering
- relatesTo: linked pages, features, database specs
</flex_block>
