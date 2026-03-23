---
id: design-tokens
title: "Design Tokens"
type: design
subtype: tokens
status: active
sequence: 1
description: "Core design tokens — colors, typography, spacing, shape, motion. Source of truth for tokens.css generation."
tags: [design, tokens, core, oklch, open-props]
createdAt: "{{created_at}}"
---

<flex_block type="instructions">
This is the source of truth for the project's visual identity. tokens.css is GENERATED from this file.

Architecture:
1. Open Props — provides sensible CSS defaults (sizing scales, easing curves, gradients)
2. Theme tokens (this file) — project-specific colors, typography, shape
3. Components.css — structural classes that consume these tokens via var()

All colors are OKLCH for perceptual uniformity. Dark mode is default.
Light mode activates via [data-theme="light"] on html.

The token interface is fixed across all 35+ FlexOS themes. Swapping a theme
means swapping ONLY the color + typography + radius-base tokens below.
Spacing, layout, transitions, and z-index are universal and never change per theme.
</flex_block>

# Design Tokens

## Philosophy

Tokens are the atoms. Every visual decision in the system resolves to a `var()` reference — never a raw value. This creates a single point of change: update a token here, and every component, prototype page, and production build inherits the change automatically.

The token set is intentionally opinionated and small. Open Props provides the utility layer (fluid type, easing, gradients). Our tokens sit on top and define the project's personality.

## Color System

OKLCH color space. Perceptually uniform — a 10% lightness shift looks the same across hues. Every theme provides the exact same semantic token names, so components never need to know which theme is active.

### Token Interface (per theme)

| Group | Tokens | Purpose |
|-------|--------|---------|
| Primary | `--color-primary`, `-hover`, `-active`, `-muted`, `-subtle` | Brand color, CTAs, links, focus rings |
| Accent | `--color-accent`, `-hover`, `-muted`, `-subtle` | Secondary highlight, complementary actions |
| Surfaces | `--color-bg`, `-bg-subtle`, `-surface`, `-surface-raised`, `-surface-overlay` | Page background, cards, modals, overlays |
| Borders | `--color-border`, `-border-subtle`, `-border-strong` | Dividers, card edges, input outlines |
| Text | `--color-text`, `-text-secondary`, `-text-muted`, `-text-on-primary`, `-text-on-accent` | Content hierarchy, contrast text on colored bg |
| Semantic | `--color-{success,warning,error,info}`, each with `-muted` | Feedback, validation, status indicators |

### Dark Mode (default)

<flex_block type="tokens">
{
  "category": "colors",
  "mode": "dark",
  "tokens": {
    "--color-primary": "oklch(62% 0.18 265)",
    "--color-primary-hover": "oklch(68% 0.20 265)",
    "--color-primary-active": "oklch(72% 0.18 265)",
    "--color-primary-muted": "oklch(62% 0.18 265 / 0.18)",
    "--color-primary-subtle": "oklch(18% 0.04 265)",
    "--color-accent": "oklch(72% 0.12 190)",
    "--color-accent-hover": "oklch(78% 0.14 190)",
    "--color-accent-muted": "oklch(72% 0.12 190 / 0.18)",
    "--color-accent-subtle": "oklch(18% 0.04 190)",
    "--color-bg": "oklch(14% 0.005 260)",
    "--color-bg-subtle": "oklch(11% 0.004 260)",
    "--color-surface": "oklch(18% 0.006 260)",
    "--color-surface-raised": "oklch(22% 0.008 260)",
    "--color-surface-overlay": "oklch(14% 0.005 260 / 0.95)",
    "--color-border": "oklch(28% 0.006 260)",
    "--color-border-subtle": "oklch(22% 0.005 260)",
    "--color-border-strong": "oklch(38% 0.008 260)",
    "--color-text": "oklch(93% 0.005 260)",
    "--color-text-secondary": "oklch(68% 0.008 260)",
    "--color-text-muted": "oklch(48% 0.006 260)",
    "--color-text-on-primary": "oklch(100% 0 0)",
    "--color-text-on-accent": "oklch(14% 0.02 190)",
    "--color-success": "oklch(68% 0.14 155)",
    "--color-success-muted": "oklch(68% 0.14 155 / 0.15)",
    "--color-warning": "oklch(78% 0.14 75)",
    "--color-warning-muted": "oklch(78% 0.14 75 / 0.15)",
    "--color-error": "oklch(65% 0.20 25)",
    "--color-error-muted": "oklch(65% 0.20 25 / 0.15)",
    "--color-info": "oklch(68% 0.12 240)",
    "--color-info-muted": "oklch(68% 0.12 240 / 0.15)"
  }
}
</flex_block>

### Light Mode

<flex_block type="tokens">
{
  "category": "colors",
  "mode": "light",
  "tokens": {
    "--color-primary": "oklch(50% 0.18 265)",
    "--color-primary-hover": "oklch(44% 0.20 265)",
    "--color-primary-active": "oklch(38% 0.20 265)",
    "--color-primary-muted": "oklch(50% 0.18 265 / 0.12)",
    "--color-primary-subtle": "oklch(96% 0.02 265)",
    "--color-accent": "oklch(62% 0.10 190)",
    "--color-accent-hover": "oklch(55% 0.12 190)",
    "--color-accent-muted": "oklch(62% 0.10 190 / 0.12)",
    "--color-accent-subtle": "oklch(96% 0.02 190)",
    "--color-bg": "oklch(98% 0.003 260)",
    "--color-bg-subtle": "oklch(96% 0.005 260)",
    "--color-surface": "oklch(100% 0 0)",
    "--color-surface-raised": "oklch(100% 0 0)",
    "--color-surface-overlay": "oklch(100% 0 0 / 0.92)",
    "--color-border": "oklch(88% 0.008 260)",
    "--color-border-subtle": "oklch(92% 0.005 260)",
    "--color-border-strong": "oklch(78% 0.012 260)",
    "--color-text": "oklch(15% 0.01 260)",
    "--color-text-secondary": "oklch(40% 0.012 260)",
    "--color-text-muted": "oklch(58% 0.010 260)",
    "--color-text-on-primary": "oklch(100% 0 0)",
    "--color-text-on-accent": "oklch(14% 0.02 190)",
    "--color-success": "oklch(55% 0.14 155)",
    "--color-success-muted": "oklch(55% 0.14 155 / 0.12)",
    "--color-warning": "oklch(72% 0.14 75)",
    "--color-warning-muted": "oklch(72% 0.14 75 / 0.12)",
    "--color-error": "oklch(52% 0.20 25)",
    "--color-error-muted": "oklch(52% 0.20 25 / 0.10)",
    "--color-info": "oklch(55% 0.14 240)",
    "--color-info-muted": "oklch(55% 0.14 240 / 0.10)"
  }
}
</flex_block>

### Shadows

Shadows shift between modes — darker and more opaque on dark backgrounds, lighter and subtle on light.

<flex_block type="tokens">
{
  "category": "shadows",
  "comment": "Dark mode values shown. Light mode uses ~0.04-0.10 opacity instead of 0.20-0.40.",
  "tokens": {
    "--shadow-sm": "0 1px 3px oklch(0% 0 0 / 0.30), 0 1px 2px oklch(0% 0 0 / 0.20)",
    "--shadow-md": "0 4px 12px oklch(0% 0 0 / 0.35), 0 2px 4px oklch(0% 0 0 / 0.20)",
    "--shadow-lg": "0 8px 24px oklch(0% 0 0 / 0.40), 0 4px 8px oklch(0% 0 0 / 0.25)",
    "--shadow-focus": "0 0 0 2px var(--color-bg), 0 0 0 4px var(--color-primary)"
  }
}
</flex_block>

## Typography

Three font stacks. Display for headings, body for everything else, mono for code and data. Themes can override these — Cupcake uses Nunito, Wireframe uses a monospace stack throughout.

<flex_block type="tokens">
{
  "category": "typography",
  "tokens": {
    "--font-display": "'Inter', system-ui, sans-serif",
    "--font-body": "'Inter', system-ui, sans-serif",
    "--font-mono": "'JetBrains Mono', 'Fira Code', monospace",
    "--font-size-xs": "0.75rem",
    "--font-size-sm": "0.875rem",
    "--font-size-base": "1rem",
    "--font-size-lg": "1.125rem",
    "--font-size-xl": "1.25rem",
    "--font-size-2xl": "1.5rem",
    "--font-size-3xl": "2rem",
    "--font-size-4xl": "2.5rem",
    "--font-size-5xl": "3.25rem",
    "--font-weight-normal": "400",
    "--font-weight-medium": "500",
    "--font-weight-semibold": "600",
    "--font-weight-bold": "700",
    "--line-height-tight": "1.2",
    "--line-height-normal": "1.5",
    "--line-height-relaxed": "1.75"
  }
}
</flex_block>

## Spacing

Quarter-rem scale. `--space-4` (1rem / 16px) is the base unit. Card padding uses `--space-5` to `--space-6`. Section padding uses `--space-12` to `--space-24`.

<flex_block type="tokens">
{
  "category": "spacing",
  "tokens": {
    "--space-1": "0.25rem",
    "--space-2": "0.5rem",
    "--space-3": "0.75rem",
    "--space-4": "1rem",
    "--space-5": "1.25rem",
    "--space-6": "1.5rem",
    "--space-8": "2rem",
    "--space-10": "2.5rem",
    "--space-12": "3rem",
    "--space-16": "4rem",
    "--space-20": "5rem",
    "--space-24": "6rem"
  }
}
</flex_block>

## Shape

`--radius-base` is the only token that changes per theme. All other radii are fixed. Cupcake uses 16px (bubbly), Lofi uses 0 (sharp), default is 8px.

<flex_block type="tokens">
{
  "category": "shape",
  "tokens": {
    "--radius-base": "8px",
    "--radius-sm": "4px",
    "--radius-md": "8px",
    "--radius-lg": "12px",
    "--radius-xl": "16px",
    "--radius-2xl": "20px",
    "--radius-full": "9999px"
  }
}
</flex_block>

## Layout

Fixed dimensions for structural elements. These don't change per theme.

<flex_block type="tokens">
{
  "category": "layout",
  "tokens": {
    "--content-max-width": "1200px",
    "--sidebar-width": "260px",
    "--sidebar-collapsed": "64px",
    "--header-height": "56px",
    "--bottom-nav-height": "56px",
    "--touch-target-min": "44px"
  }
}
</flex_block>

## Motion

Three speeds plus two easing curves. `--ease-spring` for playful bouncy interactions, `--ease-out` for standard exits.

<flex_block type="tokens">
{
  "category": "motion",
  "tokens": {
    "--transition-fast": "150ms ease-out",
    "--transition-base": "250ms ease-out",
    "--transition-slow": "400ms cubic-bezier(0.4, 0, 0.2, 1)",
    "--ease-out": "cubic-bezier(0, 0, 0.2, 1)",
    "--ease-spring": "cubic-bezier(0.34, 1.56, 0.64, 1)"
  }
}
</flex_block>

## Z-Index

Fixed stacking order. Never use raw z-index values — always reference these tokens.

<flex_block type="tokens">
{
  "category": "z-index",
  "tokens": {
    "--z-base": "1",
    "--z-raised": "10",
    "--z-dropdown": "100",
    "--z-sticky": "200",
    "--z-sidebar": "300",
    "--z-overlay": "400",
    "--z-modal": "500",
    "--z-toast": "700",
    "--z-tooltip": "800"
  }
}
</flex_block>

## Theme System

35+ themes available in the FlexOS registry. Each theme provides the exact same color + typography + radius-base tokens. Everything else (spacing, layout, motion, z-index) is universal.

To switch themes: set `data-theme="{name}"` on `<html>`. To add a custom theme: define the color token interface above for both light and dark modes.

Default theme for new projects is derived from the project's chosen `brand.themeColor` in project.json. The provisioning system converts the hex color to an OKLCH hue and generates a full token set.
