---
version: alpha
name: SoluteLabs
description: Purple-accented, typographically confident, restrained. Dark by default, light for collateral.
colors:
  # Brand primitives
  fresh-purple: "#6622CB"
  bright-orange: "#FF4D00"
  charcoal: "#171717"
  elevated: "#1F1F1F"
  white: "#FFFFFF"
  purple-100: "#E2CFFF"
  purple-200: "#C2A7EA"
  purple-300: "#4D1A98"
  magnolia: "#FBF6FF"
  grey-100: "#F1F5F9"
  grey-200: "#E2E8F0"
  grey-300: "#475569"
  grey-400: "#374252"
  # Semantic: surfaces (use for background-color)
  surface: "#171717"
  surface-raised: "#1F1F1F"
  surface-accent: "#6622CB"
  # Semantic: foreground (use for color/text)
  foreground: "#FFFFFF"
  foreground-muted: "#FFFFFFCC"
  foreground-faint: "#FFFFFF99"
  foreground-accent: "#C2A7EA"
  foreground-inverse: "#171717"
  # Semantic: edges (use for border-color)
  edge: "#FFFFFF26"
  edge-subtle: "#FFFFFF1A"
  edge-strong: "#FFFFFF4D"
  edge-accent: "#6622CB"
  edge-highlight: "#FF4D00"
  # Brand accents (multi-use)
  accent-primary: "#6622CB"
  accent-secondary: "#FF4D00"
typography:
  display:
    fontFamily: Archivo
    fontSize: 48px
    fontWeight: 500
    lineHeight: 56px
    letterSpacing: -0.02em
  hero:
    fontFamily: Archivo
    fontSize: 40px
    fontWeight: 500
    lineHeight: 56px
    letterSpacing: -0.02em
  heading:
    fontFamily: Archivo
    fontSize: 32px
    fontWeight: 500
    lineHeight: 60px
    letterSpacing: -0.02em
  title-lg:
    fontFamily: Archivo
    fontSize: 28px
    fontWeight: 500
    lineHeight: 44px
    letterSpacing: -0.02em
  title:
    fontFamily: Archivo
    fontSize: 24px
    fontWeight: 500
    lineHeight: 40px
    letterSpacing: -0.02em
  title-sm:
    fontFamily: Archivo
    fontSize: 22px
    fontWeight: 500
    lineHeight: 36px
    letterSpacing: -0.02em
  lead:
    fontFamily: Manrope
    fontSize: 20px
    fontWeight: 400
    lineHeight: 34px
    letterSpacing: 0.01em
  body:
    fontFamily: Manrope
    fontSize: 18px
    fontWeight: 400
    lineHeight: 30px
    letterSpacing: 0.01em
  label:
    fontFamily: Archivo
    fontSize: 16px
    fontWeight: 500
    lineHeight: 16px
    letterSpacing: 0em
  button-secondary-label:
    fontFamily: Archivo
    fontSize: 18px
    fontWeight: 500
    lineHeight: 30px
    letterSpacing: 0em
  eyebrow:
    fontFamily: Archivo
    fontSize: 16px
    fontWeight: 600
    lineHeight: 16px
    letterSpacing: 0.08em
rounded:
  sm: 6px
  md: 8px
  lg: 12px
  xl: 16px
  pill: 9999px
spacing:
  xs: 4px
  sm: 8px
  md: 16px
  lg: 24px
  xl: 32px
  2xl: 48px
  section: 120px
  container: 1440px
  gutter: 16px
  gutter-lg: 24px
components:
  button-primary:
    backgroundColor: "{colors.white}"
    textColor: "{colors.foreground-inverse}"
    typography: "{typography.label}"
    rounded: "{rounded.md}"
    padding: 10px 20px
  button-primary-hover:
    backgroundColor: "#FFFFFFE6"
  button-primary-active:
    backgroundColor: "#FFFFFFCC"
  button-secondary:
    backgroundColor: transparent
    textColor: "{colors.foreground}"
    typography: "{typography.button-secondary-label}"
    rounded: "{rounded.md}"
    padding: 18px 32px
  button-secondary-hover:
    backgroundColor: "#FFFFFF0D"
  button-secondary-active:
    backgroundColor: "#FFFFFF14"
  card:
    backgroundColor: "{colors.surface-raised}"
    textColor: "{colors.foreground}"
    rounded: "{rounded.lg}"
    padding: 18px 24px
  input:
    backgroundColor: "{colors.surface-raised}"
    textColor: "{colors.foreground}"
    typography: "{typography.body}"
    rounded: "{rounded.sm}"
    padding: 12px 16px
    height: 44px
---

## Overview

SoluteLabs is an AI-native product engineering studio. The visual identity is **purple-accented, typographically confident, and restrained**. Think premium tech studio, not startup energy.

The UI is dark by default (`#171717`). Decks, proposals, print, and documents use light mode (white background). Both modes share the same semantic tokens. Components don't change, only token values flip.

Purple (`#6622CB`) is a spotlight, not a wash. It covers roughly 20% of surface area: a hero glow, an accent section, a focus ring. Orange (`#FF4D00`) is rarer still, reserved for stat suffixes (`80%+`), eyebrow bullets, and checkmark icons.

For the full design system with Tailwind classes, code examples, and implementation details, see [`design-system/README.md`](design-system/README.md).

## Colors

A tight four-color palette: charcoal, fresh purple, bright orange, white. We don't add colors to solve problems. We use the ones we have.

- **Charcoal (#171717):** Every dark surface. Page background, inverse text.
- **Fresh Purple (#6622CB):** Core brand accent. Hero sections, focus states, accent surfaces.
- **Bright Orange (#FF4D00):** Secondary accent, used sparingly. The `+` on stats, eyebrow square bullets, checkmarks. Never as a button background.
- **White (#FFFFFF):** Primary text on dark, primary button background.
- **Elevated (#1F1F1F):** Slightly lighter than charcoal. Cards, modals, raised surfaces.

### Semantic token system

Components never reference raw hex values. They use semantic tokens organized by CSS property:

- **Surfaces** (`surface`, `surface-raised`, `surface-accent`) for `background-color`
- **Foreground** (`foreground`, `foreground-muted`, `foreground-faint`, `foreground-accent`, `foreground-inverse`) for `color`
- **Edges** (`edge`, `edge-subtle`, `edge-strong`, `edge-accent`, `edge-highlight`) for `border-color`
- **Accents** (`accent-primary`, `accent-secondary`) for brand expression anywhere

### Light mode

Activate with `class="light"` on any container. Key swaps:

| Token | Dark | Light |
|:------|:-----|:------|
| `surface` | `#171717` | `#FFFFFF` |
| `surface-raised` | `#1F1F1F` | `#FBF6FF` (magnolia) |
| `foreground` | `#FFFFFF` | `#171717` |
| `foreground-muted` | `white/80%` | `#374252` |
| `foreground-accent` | `#C2A7EA` | `#4D1A98` |
| `edge` | `white/15%` | `#E2E8F0` |

Brand accents (`accent-primary`, `accent-secondary`) and `surface-accent` do not change between modes.

## Typography

Two font families. No substitutions.

- **Archivo** for titles, headings, display text, button labels, eyebrows, and stats. Geometric and confident at large sizes.
- **Manrope** for body copy, descriptions, and lead paragraphs. Readable and modern at text sizes.

Self-host both. Do not use Google CDN at runtime. Fallback stack: `system-ui, -apple-system, sans-serif`. In Tailwind, `font-sans` is aliased to Manrope (the default body font).

### Hierarchy

| Level | Family | Size | Weight | Use |
|:------|:-------|:-----|:-------|:----|
| Display | Archivo | 48px | 500 | Hero headline |
| Hero | Archivo | 40px | 500 | H1 |
| Heading | Archivo | 32px | 500 | H2, section headings |
| Title LG | Archivo | 28px | 500 | H3 |
| Title | Archivo | 24px | 500 | Card titles |
| Title SM | Archivo | 22px | 500 | Eyebrow-adjacent headings |
| Lead | Manrope | 20px | 400 | Lead paragraphs |
| Body | Manrope | 18px | 400 | Default paragraph copy |
| Label | Archivo | 16px | 500 | Button text, compact labels |
| Eyebrow | Archivo | 16px | 600 | ALL-CAPS labels, `letter-spacing: 0.08em` |

### Letter spacing

- Headings and display: `-0.02em` (tight)
- Body copy in Manrope: `0.01em` (wide)
- Eyebrows: `0.08em` (tracked wide, always uppercase)

## Layout & Spacing

Content max-width is 1440px. Background effects (glows, gradients) extend to viewport edge; content stays inside the container.

Spacing follows a 4px base grid. Key intervals:

| Intent | Value |
|:-------|:------|
| Hairline gap | 4px |
| Tight stack | 8px |
| Standard gap | 16px |
| Card padding | 18px vertical, 24px horizontal |
| Button padding | 10px vertical, 20px horizontal |
| Section internal | 48px |
| Between page sections | 120px |

Side gutters: 16px mobile, 24px desktop.

## Elevation & Depth

Dark surfaces get depth from **elevated background + border**, not shadows. A card is `surface-raised` (#1F1F1F) with a 1px `edge-subtle` border on a `surface` (#171717) page. No drop shadows on dark backgrounds.

Shadows exist for rare floating elements:

| Level | Value | Use |
|:------|:------|:----|
| SM | `0 1px 2px rgba(0,0,0,0.3)` | Subtle lift |
| MD | `0 4px 12px rgba(0,0,0,0.4)` | Dropdowns |
| LG | `0 12px 32px rgba(0,0,0,0.5)` | Modals |
| Glow | `0 0 120px rgba(102,34,203,0.4)` | Hero purple glow only |

Light mode uses softer shadow values (lower opacity). Cards in light mode use magnolia (`#FBF6FF`) with subtle shadows for lift.

## Shapes

Slightly larger radii than defaults. Consistent across all elements.

| Scale | Value | Use |
|:------|:------|:----|
| SM | 6px | Inputs, small elements |
| MD | 8px | Buttons |
| LG | 12px | Cards |
| XL | 16px | Large surfaces, feature modules |
| Pill | 9999px | Tags, badges (rare) |

## Components

Three components are specified. Each uses semantic tokens exclusively.

### Button (Primary)

Solid white. The single most important action on screen. One per view.

- White background, charcoal text, Archivo Medium 16px
- 8px radius, 10px/20px padding
- Hover: white/90%. Active: white/80%. Transitions: 120ms.
- Focus: 2px purple outline, 2px offset
- Disabled: 40% opacity

### Button (Secondary)

Ghost/outlined. Supporting actions like "All Case Studies" or "Explore More".

- Transparent background, white text, 1px `edge` border
- Archivo Medium 18px (intentionally larger than primary for visual weight with more padding)
- 8px radius, 18px/32px padding
- Hover: white/5% fill, border shifts to `edge-strong`

### Card

Dark background, restrained border. Used for case studies, features, stats.

- `surface-raised` background, 1px `edge-subtle` border, 12px radius
- Three optional zones: media, body, footer
- Stats inside cards use Archivo (display text). The `+` suffix is always `accent-secondary` (orange).
- Highlighted variant: border shifts to `edge-highlight` (orange). All else unchanged.

### Input

Form inputs for contact, newsletter, search.

- `surface-raised` background, 1px `edge` border, 6px radius
- Manrope Regular 18px, 12px/16px padding, 44px min-height
- Focus: border shifts to `edge-accent` (purple). No shadow, no extra outline.
- Labels always above the input. Never placeholder-only.

For full Tailwind class examples and all states, see [`design-system/components.md`](design-system/components.md).

## Do's and Don'ts

- Do use semantic tokens in components (`bg-surface-raised`, not `bg-[#1F1F1F]`). This is what makes light mode work without rewriting components.
- Do limit purple to ~20% of surface area. A hero glow, an accent section. Not everything.
- Do use Archivo for all headings, stats, and button labels. Manrope for body copy only.
- Do precede eyebrow labels with an orange square (`w-2 h-2`). Always uppercase, tracked wide.
- Do keep one primary button per view. If you need two, one is secondary.
- Don't use drop shadows on dark surfaces. Depth = elevated background + subtle border.
- Don't use orange as a button background. It's for stat suffixes, checkmarks, and eyebrow bullets.
- Don't add colors. If you need error/success states, note it as a v1.x proposal.
- Don't use Inter, Geist, or Space Grotesk. The fonts are Archivo and Manrope. Fallback: `system-ui`.
- Don't use emoji in UI. Ever.
- Don't use em-dashes in body copy. Use periods and sentence breaks.
- Don't create a "tertiary" button variant. Use a text link instead.
- Do place icons right for navigation (arrow), left for actions (back, add). No label animation, color/background transitions only.
- Don't mix rounded and sharp corners in the same view. Match existing radii (cards = `rounded-lg`, buttons = `rounded-md`).
