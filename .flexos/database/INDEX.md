---
id: database-index
title: "Database Specs"
type: index
subtype: folder
status: active
---

<flex_block type="instructions">
Database specs define HOW DATA IS STRUCTURED. Framework-agnostic.

SUBTYPES:
- collection: A data entity/table (e.g., dogs, users, applications)
- api: An external API integration (e.g., Stripe payments, SendGrid email)
- store: Client-side state (e.g., cart, UI preferences, draft forms)

NAMING: NNN-{subtype}-{slug}.md
EXAMPLE: 001-collection-dogs.md, 005-api-stripe.md, 007-store-cart.md

Each file should include:
- A <flex_block type="schema"> defining the entity structure
- Prose describing relationships, business rules, access patterns
- relatesTo: linked features, pages, flows that use this data

The schema block has: collection name, fields array (name, type, required,
description, values for enums, ref for references), indexes, subcollections.
</flex_block>
