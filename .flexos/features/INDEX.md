---
id: features-index
title: "Feature Specs"
type: index
subtype: folder
status: active
---

<flex_block type="instructions">
Feature specs define WHAT the app does. Each file is one feature.

SUBTYPES:
- primary: Core features that define the app (e.g., "Dog Profiles", "Adoption Applications")
- secondary: Supporting features reused across primaries (e.g., "Photo Upload", "Email Notifications")

NAMING: NNN-{subtype}-{slug}.md
EXAMPLE: 001-primary-dog-profiles.md, 004-secondary-photo-upload.md

Each file should include:
- What the feature does (user-facing description)
- Key behaviors (specific interactions and rules)
- Acceptance criteria (testable requirements)
- relatesTo: linked page specs, flow specs, database specs

STATUS: roadmap (planned for future), active (being built/live), archived (removed).
</flex_block>
