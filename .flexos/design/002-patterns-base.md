---
id: design-patterns-base
title: "Component Patterns"
type: design
subtype: patterns
status: active
sequence: 2
description: "Core semantic CSS primitives — the universal class vocabulary for prototypes and builds."
tags: [design, patterns, css, semantic, core]
relatesTo: [design/001-tokens-design-system.md]
createdAt: "{{created_at}}"
---

<flex_block type="instructions">
Source of truth for the structural CSS component library. components.css is GENERATED from this file.

This is an UNSTYLED semantic vocabulary. Every class resolves to var() token references.
Swap tokens.css → entire look changes. Structure stays the same.

Rules:
- Zero hardcoded values. Everything via var().
- Modifier pattern: .component-variant, .component-size, .component.state
- Mobile-first. Touch targets 44px minimum.
- Hover states inside @media (hover: hover) only.
- Reduced motion via @media (prefers-reduced-motion).
- Open Props provides utility foundation.
- Flat classes. No nesting, no BEM, no utility-first.

This is the CORE set — ~15 primitives. Extended patterns (carousels, timelines,
masonry, swipe decks) live in the shared pattern libraries, not here.
</flex_block>

# Core Component Patterns

## Modifiers

Consistent across all components:

| Type | Pattern | Example |
|------|---------|---------|
| Variant | `.component-{variant}` | `.btn-primary`, `.card-accent` |
| Size | `.component-{size}` | `.btn-sm`, `.btn-lg` |
| State | `.component.{state}` | `.nav-item.active`, `.input.error` |
| Behavior | `.component-{behavior}` | `.card-hover`, `.btn-loading` |

---

## Layout

### Container
`.container` — max-width wrapper, responsive inline padding (space-4 → space-6 → space-8).

### App Shell
`.app-shell` — flex row, full dvh. The authenticated app frame.
`.app-content` — flex-1 column, takes remaining width.
`.page-header` — top bar with title + actions, border-bottom.
`.page-title` — 2xl bold heading.
`.page-subtitle` — sm secondary text below title.

### Sections
`.section` — vertical padding block for marketing pages. Adjacent sections get border-top.
`.section-label` — mono uppercase primary overline.
`.section-title` — 2xl heading.
`.section-subtitle` — base secondary, max-width 600px.

---

## Sidebar

`.sidebar` — fixed-width, full-height, sticky, surface bg, border-right. Hidden on mobile.
`.sidebar-header` — logo area, min-height matches header.
`.sidebar-nav` — scrollable nav area.
`.sidebar-section-label` — uppercase group label.
`.sidebar-footer` — pinned bottom area.

---

## Navigation

### Sidebar Nav
`.nav` — flex column, gap.
`.nav-item` — full-width row, icon + label, touch target, rounded. `.active` state.
`.nav-item-icon` — 18px icon slot.

### Top Navbar
`.navbar` — sticky top, blur backdrop, border-bottom.
`.navbar-brand` — logo + name, bold display font.
`.navbar-actions` — right-aligned buttons.

### Bottom Nav
`.bottom-nav` — fixed bottom, full width, surface bg, border-top, safe-area padding.
`.bottom-nav-item` — flex column, icon above label, touch target. `.active` state.

---

## Buttons

`.btn` — base. Inline-flex, centered, gap, rounded, touch target min, active scale(0.97).

| Variant | Class |
|---------|-------|
| Filled primary | `.btn-primary` |
| Outline | `.btn-secondary` |
| Text only | `.btn-ghost` |
| Accent filled | `.btn-accent` |
| Destructive | `.btn-error` |

| Size | Class | Height |
|------|-------|--------|
| Small | `.btn-sm` | 32px |
| Default | — | 44px |
| Large | `.btn-lg` | 52px |

| Behavior | Class |
|----------|-------|
| Full width | `.btn-block` |
| Icon only | `.btn-icon` |
| Spinner | `.btn-loading` |
| Disabled | `.btn[disabled]` |

---

## Cards

`.card` — surface bg, border, radius-lg, overflow hidden.
`.card-body` — content padding.
`.card-header` — top bar, border-bottom, flex between.
`.card-footer` — bottom bar, border-top, subtle bg.
`.card-hover` — lift + shadow on desktop hover.
`.card-accent` — left border in primary.

### Stat Cards
`.stats-bar` — auto-fit grid (min 140px).
`.stat-card` — individual stat container.
`.stat-label` — uppercase muted label.
`.stat-value` — 3xl bold number.
`.stat-sub` — secondary context.

---

## Badges

`.badge` — inline pill, xs semibold.

`.badge-primary`, `.badge-accent`, `.badge-success`, `.badge-warning`, `.badge-error`, `.badge-info`, `.badge-neutral`

Each uses the semantic `-muted` bg + solid text color.

---

## Forms

### Controls
`.input`, `.select`, `.textarea` — full width, border, rounded, focus ring, touch target. 16px font on mobile.

### Structure
`.form-group` — flex column, label + control + hint/error.
`.form-label` — sm medium secondary, above control.
`.form-hint` — xs muted, below control.
`.form-error` — xs error color, below control.

### States
`.input.error` — error border + error focus ring.
`.input:focus` — primary border + primary muted ring.

---

## Tables

`.table-wrapper` — surface container, border, radius, overflow hidden.
`.table` — full width, collapsed borders.
`th` — uppercase xs muted header cells.
`td` — sm text, border-bottom between rows.

Desktop: rows highlight on hover.

---

## Tabs

`.tab-bar` — flex row, bottom border.
`.tab` — padding, secondary text, 2px underline. `.active` = primary text + primary underline.

Touch target enforced on mobile. Horizontal scroll if overflow.

---

## Modal

`.modal-backdrop` — fixed fullscreen, dark translucent, flex-center.
`.modal` — surface, max-width 480px, radius-xl, shadow-lg.
`.modal-header` — title + close, border-bottom.
`.modal-body` — content padding.
`.modal-footer` — actions, border-top, right-aligned.

Animation: fade backdrop + scale/slide modal.

---

## Toast

`.toast-container` — fixed bottom-right, flex column stack.
`.toast` — surface-raised, border, shadow, flex row.
`.toast-success`, `.toast-error`, `.toast-warning`, `.toast-info` — left border color.

Animation: slide up + fade in.

---

## Empty State

`.empty-state` — flex column centered, generous padding.
`.empty-icon` — 48px rounded icon container.
`.empty-title` — xl medium.
`.empty-desc` — sm secondary, max-width 300px.

---

## Progress

`.progress` — track, full width, 6px, rounded.
`.progress-bar` — fill, primary bg, animated width.

---

## Grid

`.grid` — display grid, gap.
`.grid-2`, `.grid-3`, `.grid-4` — fixed columns, collapse responsively (4→2→1).

### Flex Utilities
`.flex`, `.flex-col`, `.flex-wrap`, `.items-center`, `.justify-between`
`.gap-1` through `.gap-6`

### Text Utilities
`.text-xs` through `.text-3xl` — sizes.
`.text-muted`, `.text-secondary`, `.text-primary`, `.text-accent` — colors.
`.font-medium`, `.font-semibold`, `.font-bold`, `.font-mono` — weights/family.
`.truncate` — overflow ellipsis.

---

## Theme Toggle

`.theme-toggle` — button, no bg, secondary text, hover muted bg. Toggles `data-theme` on html.

---

## Animation Keyframes

`fade-in`, `modal-in`, `toast-in`, `spin` — the four core animations. All respect `prefers-reduced-motion`.

---

## Accessibility (enforced globally)

- Touch targets: 44px minimum on all interactive elements
- Focus: `--shadow-focus` ring on `:focus-visible`
- Hover: `@media (hover: hover) and (pointer: fine)` only
- Motion: `@media (prefers-reduced-motion)` collapses all animation
- Zoom: 16px min font on mobile inputs
- Safe areas: bottom-nav accounts for `env(safe-area-inset-bottom)`
- Selection: `--color-primary-muted` background
