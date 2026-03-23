---
id: technical-index
title: "Technical Specs"
type: index
subtype: folder
status: active
---

<flex_block type="instructions">
Technical specs define WHAT TECHNOLOGY IS USED AND WHY.

These are decision documents, not implementation guides. They explain
the choice of framework, database, auth provider, etc. and the reasoning
behind each decision. Implementation details belong in reference docs.

SUBTYPES:
- stack: Framework and platform choices (e.g., "We use Nuxt because...")
- integration: Third-party services (e.g., "Stripe for payments because...")
- infrastructure: Hosting, deployment, monitoring (e.g., "Vercel because...")
- auth: Authentication and authorization setup (e.g., "Firebase Auth with Google OAuth")

NAMING: NNN-{subtype}-{slug}.md
EXAMPLE: 001-stack-nuxt-firebase.md, 003-integration-stripe.md

When technical specs change, the reference/ folder should be updated
with new SDK documentation for the builder AI.
</flex_block>
