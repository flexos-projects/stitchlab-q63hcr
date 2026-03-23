# {{project_name}}

> This is your FlexOS project folder. Everything about your product lives here — from high-level vision to detailed specs to interactive prototypes.

## What's Inside

| Folder | What It Contains | Key Files |
|--------|-----------------|-----------|
| `docs/` | 9 core docs (000-008) + cross-cutting guides | Core summaries, guides from 100+ |
| `vision/` | Goals, constraints, audience, brand identity | Individual vision specs |
| `features/` | What the app does — primary and secondary features | Individual feature specs |
| `pages/` | Routes, components, layouts, overlays | Individual page specs |
| `flows/` | User journeys, auth flows, backend processes | Individual flow specs |
| `database/` | Collection schemas, API integrations, state stores | Individual database specs |
| `design/` | Design tokens, CSS patterns, brand reference | `001-tokens-design-system.md`, `002-patterns-base.md` |
| `technical/` | Stack decisions, integrations, infrastructure | Individual technical specs |
| `content/` | Seed data collections (default: `context/`) | `context/001-about.md` |
| `assets/` | Asset registry — logos, icons, fonts, images | Individual asset specs |
| `prototype/` | Interactive HTML prototypes + shared CSS + mock data | `pages/index.html`, `shared/tokens.css` |
| `reference/` | SDK/framework documentation for the builder AI | Imported docs |
| `builds/` | Build lifecycle — config, agent, tasks, logs | `001-first-deploy/` |
| `spaces/` | Focused conversation sessions with context | `001-kickoff/` |
| `commits/` | Auto-generated changelog entries | Created automatically |
| `imports/` | Raw imported content before triage | Landing zone |

## Key Files

- **`project.json`** — Project configuration (name, slug, theme color)
- **`docs/001-vision.md`** — Vision & strategy overview (regenerated from vision specs)
- **`design/001-tokens-design-system.md`** — Color tokens (light + dark), typography, spacing
- **`design/002-patterns-base.md`** — CSS component patterns (buttons, cards, grids, nav)
- **`prototype/pages/index.html`** — Showcase page (design system demo + project overview)
- **`prototype/shared/tokens.css`** — CSS custom properties (light + dark mode)
- **`prototype/shared/components.css`** — Reusable component classes
- **`prototype/sitemap.md`** — Page manifest + Vercel deployment config
- **`builds/001-first-deploy/config.md`** — First build configuration
- **`content/context/001-about.md`** — Background info about the project

## How FlexOS Works

1. **Talk** — Tell the AI about your project in natural language
2. **Specs appear** — The AI creates numbered spec files in the right folders
3. **Core docs update** — Holistic summaries (docs/001-008) regenerate as specs evolve
4. **Prototypes generate** — Visual HTML previews of your pages
5. **Build executes** — AI reads everything and produces production code
6. **Commits track** — Every change is recorded automatically

## File Format

Every `.md` file follows the FlexDoc format:
- **YAML frontmatter** — id, title, type, subtype, status, tags, relatesTo
- **flex_blocks** — Structured data in `<flex_block type="...">` tags
- **Markdown** — Human-readable documentation and context

Block types: `schema`, `flow`, `tokens`, `config`, `asset`, `sitemap`, `instructions` (AI context, hidden from tab bar)

## Theme

This project supports **light and dark mode**. Design tokens define values for both modes. The prototype toggle (moon/sun icon in nav) switches themes with `localStorage` persistence. OS preference is respected as fallback.

## Deployment

Prototypes deploy to **{{project_slug}}.flexos.site** via GitHub Actions (`.github/workflows/deploy-preview.yml`). Push to main auto-deploys. Manual deploy via `workflow_dispatch`.

## Status

This project was just created. Core documents and prototypes will be personalized with your project name and color choice.
