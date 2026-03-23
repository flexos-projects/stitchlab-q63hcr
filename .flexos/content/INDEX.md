---
id: content-index
title: "Content"
type: index
subtype: folder
status: active
---

<flex_block type="instructions">
Content specs define WHAT DATA THE PROJECT NEEDS beyond the database schema.
Each subfolder is a collection. Each collection has:
- INDEX.md (type: content, subtype: collection) — defines what this collection is
- Numbered record files (type: content, subtype: record) — individual entries

The default "context" collection ships with every project as a catch-all
for unstructured knowledge the user provides: company bios, brand values,
competitor info, marketing copy, etc. Anything the AI should know that
doesn't fit a structured collection.

Other collections are created as needed: blogs, testimonials, FAQs, etc.

NAMING: {collection-name}/NNN-{slug}.md
EXAMPLE: context/001-about.md, dogs/001-luna.md, blog/001-launch-post.md
</flex_block>
