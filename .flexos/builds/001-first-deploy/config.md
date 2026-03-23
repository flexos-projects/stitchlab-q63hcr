---
id: build-001-config
title: "First Deploy Configuration"
description: "Tech stack and deployment targets for the initial build"
type: build
subtype: config
status: draft
sequence: 1
tags: [build, config, first-deploy]
relatesTo: [docs/007-technical.md]
createdAt: "{{created_at}}"
---

# First Deploy Configuration

This is the configuration for the first build. It converts the prototype showcase page into a real Nuxt application page.

<flex_block type="config">
{
  "build": {
    "name": "001-first-deploy",
    "version": "0.1.0",
    "status": "planning",
    "scope": "Convert prototype index.html to Nuxt page"
  },
  "stack": {
    "framework": "Nuxt 4",
    "language": "TypeScript",
    "styling": "UnoCSS / Tailwind",
    "hosting": "Vercel"
  },
  "output": {
    "repo": "github:{{github_owner}}/{{github_repo}}",
    "branch": "main",
    "deployUrl": "https://{{project_slug}}.vercel.app"
  },
  "constraints": {
    "maxBuildTasks": 1,
    "targetDuration": "1 hour",
    "codeStandards": "TypeScript strict, Vue 3 Composition API"
  }
}
</flex_block>

## Scope

This build has ONE task: convert the prototype showcase page into a Nuxt page. This proves the build pipeline works end-to-end.

### In Scope

- Convert prototype/pages/index.html to a Nuxt page component
- Migrate design tokens to the Nuxt project
- Deploy to Vercel

### Out of Scope

- Everything else — features, auth, database, etc.
- Those come in build 002+
