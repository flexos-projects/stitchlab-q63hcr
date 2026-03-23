---
id: builds-index
title: "Builds"
type: index
subtype: folder
status: active
---

<flex_block type="instructions">
Build folders are numbered sequentially: 001-mvp, 002-auth, etc.
Each folder contains the full build lifecycle:

FILES IN EACH BUILD FOLDER:
- config.md (type: build, subtype: config) — stack, constraints, deploy targets
- agent.md (type: build, subtype: agent) — AI agent instructions for this build
- log.md (type: build, subtype: log) — chronological progress record
- tasks/NNN-{slug}.md (type: build, subtype: task) — executable tasks with status + dependencies
- debug/NNN-{slug}.md (type: build, subtype: debug) — bug reports with severity

BUILD-MANIFEST.json — machine-readable build state (JSON, not FlexDoc)

TASK STATUS: pending → in-progress → done/failed/blocked
DEBUG SEVERITY: critical, high, medium, low
</flex_block>
