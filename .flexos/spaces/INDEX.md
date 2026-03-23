---
id: spaces-index
title: "Spaces"
type: index
subtype: folder
status: active
---

<flex_block type="instructions">
Spaces are focused session workspaces. Each space is a numbered subfolder.

STRUCTURE: spaces/NNN-{slug}/
- space.md (type: space, subtype: session) — defines the space topic + reading list
- NOTES.md — append-only log of what was discussed/decided

The space.md file uses relatesTo to pull in context automatically.
When a user selects a space, the AI loads all related files as context.

NAMING: NNN-{slug}/ → 001-kickoff/, 002-design-review/
</flex_block>
