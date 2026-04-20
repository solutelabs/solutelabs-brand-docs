# SoluteLabs Design Tokens

The token layer. If you're generating code, this tells you what values to use. If you're designing new components, this tells you what's allowed.

**Which file should I use?**
- Tailwind v4 project → use `tailwind.css` (defines the same tokens as Tailwind theme values)
- Any other stack → use `tokens.css` (plain CSS custom properties)
- This file → documentation of intent, rationale, and usage rules

---

## Philosophy

Dark-first. Tight four-color palette: charcoal, fresh purple, bright orange, white. We don't add colors to solve problems — we use the ones we have.

Two type families: **Archivo** (titles) and **Manrope** (body). No third family.

v1 is dark mode only. Light mode is v2.

---

## Color

### Brand primitives

Raw values. Never use directly in components — always go through semantic tokens.

| Name | Value | What it is |
|---|---|---|
| `fresh-purple` | `#6622CB` | Core brand accent |
| `bright-orange` | `#FF4D00` | Secondary accent (sparingly) |
| `charcoal` | `#171717` | The black — every dark surface |
| `white` | `#FFFFFF` | Primary text on dark |
| `elevated` | `#1F1F1F` | Slightly lighter black for raised surfaces |

### Purple tints

| Name | Value | Intent |
|---|---|---|
| `purple-100` | `#E2CFFF` | Reserved for light mode |
| `purple-200` | `#C2A7EA` | Inline text accent on dark surfaces |
| `purple-300` | `#4D1A98` | Reserved for light mode |

### Semantic tokens

What components actually reference. Organized by what CSS property they're typically used with.

**Surfaces** (background-color)

| Token | Value | Tailwind class | Use for |
|---|---|---|---|
| `surface` | `#171717` | `bg-surface` | Page background |
| `surface-raised` | `#1F1F1F` | `bg-surface-raised` | Cards, modals, elevated panels |
| `surface-accent` | `#6622CB` | `bg-surface-accent` | Purple hero sections |

**Foreground** (color / text)

| Token | Value | Tailwind class | Use for |
|---|---|---|---|
| `foreground` | `#FFFFFF` | `text-foreground` | Headlines, primary copy |
| `foreground-muted` | `white @ 80%` | `text-foreground-muted` | Body paragraphs, descriptions |
| `foreground-faint` | `white @ 60%` | `text-foreground-faint` | Captions, metadata |
| `foreground-accent` | `#C2A7EA` | `text-foreground-accent` | Inline purple emphasis |
| `foreground-inverse` | `#171717` | `text-foreground-inverse` | Text on white surfaces |

**Edges** (border-color)

| Token | Value | Tailwind class | Use for |
|---|---|---|---|
| `edge` | `white @ 15%` | `border-edge` | Standard borders (cards, inputs) |
| `edge-subtle` | `white @ 10%` | `border-edge-subtle` | Barely-there dividers |
| `edge-strong` | `white @ 30%` | `border-edge-strong` | Emphasized / hover borders |
| `edge-accent` | `#6622CB` | `border-edge-accent` | Focus/active state (purple) |
| `edge-highlight` | `#FF4D00` | `border-edge-highlight` | Featured/selected (orange) |

**Accents** (multi-use)

| Token | Value | Tailwind class | Use for |
|---|---|---|---|
| `accent-primary` | `#6622CB` | `bg-accent-primary` / `text-accent-primary` | Primary brand expression |
| `accent-secondary` | `#FF4D00` | `text-accent-secondary` | The orange `+` on stats, checkmarks |

---

## Typography

### Families

```
Title → Archivo (geometric, confident at large sizes)
Body  → Manrope (readable, modern at smaller sizes)
```

Self-host both. Do not use Google CDN at runtime.

**Font loading example (Next.js):**

```ts
import { Archivo, Manrope } from 'next/font/google';

const archivo = Archivo({ subsets: ['latin'], variable: '--font-title' });
const manrope = Manrope({ subsets: ['latin'], variable: '--font-body' });

// In layout: <body className={`${archivo.variable} ${manrope.variable}`}>
```

**Font loading example (@font-face):**

```css
@font-face {
  font-family: 'Archivo';
  src: url('/fonts/archivo-variable.woff2') format('woff2');
  font-weight: 400 700;
  font-display: swap;
}
@font-face {
  font-family: 'Manrope';
  src: url('/fonts/manrope-variable.woff2') format('woff2');
  font-weight: 400 700;
  font-display: swap;
}
```

### Weights

| Name | Value | Use |
|---|---|---|
| Regular | 400 | Body copy |
| Medium | 500 | Headings, button labels |
| Semibold | 600 | Eyebrows, bold labels |
| Bold | 700 | Rare — strong emphasis only |

### Sizes

Named by intent, not arbitrary scale numbers:

| Token | Size | Line-height | Tailwind class | Typical use |
|---|---|---|---|---|
| `label` | 16px | 16px | `text-label` | Button text, compact labels |
| `body` | 18px | 30px | `text-body` | Default paragraph copy |
| `lead` | 20px | 34px | `text-lead` | Lead paragraphs |
| `title-sm` | 22px | 36px | `text-title-sm` | Eyebrow-adjacent headings |
| `title` | 24px | 40px | `text-title` | Card titles, section subheads |
| `title-lg` | 28px | 44px | `text-title-lg` | H3 |
| `heading` | 32px | 60px | `text-heading` | H2, section headings |
| `hero` | 40px | 56px | `text-hero` | H1 |
| `display` | 48px | 56px | `text-display` | Hero headline |

**Note:** Tailwind's built-in `text-xs` (12px), `text-sm` (14px), `text-base` (16px) remain available and unmodified. Use them for genuinely small UI text that falls below the brand type scale.

### Letter spacing

| Token | Value | Tailwind class | Use for |
|---|---|---|---|
| `tight` | `-0.02em` | `tracking-tight` | All headings and display text |
| `normal` | `0` | `tracking-normal` | Default |
| `wide` | `0.01em` | `tracking-wide` | Body copy in Manrope |
| `eyebrow` | `0.08em` | `tracking-eyebrow` | ALL-CAPS eyebrow labels |

### Standard pairings

Copy these directly — they match the homepage:

```
Display/Hero  → font-title font-medium text-display tracking-tight
H1            → font-title font-medium text-hero tracking-tight
H2            → font-title font-medium text-heading tracking-tight
H3            → font-title font-medium text-title-lg tracking-tight
Card title    → font-title font-medium text-title tracking-tight
Eyebrow       → font-title font-semibold text-label tracking-eyebrow uppercase
Body lead     → font-body text-lead tracking-wide
Body          → font-body text-body tracking-wide
Body small    → font-body text-label tracking-wide
Button label  → font-title font-medium text-label tracking-normal
```

---

## Spacing

Tailwind v4 calculates spacing dynamically: class `p-N` = `N × 4px`. Half-steps work: `p-2.5` = 10px, `p-4.5` = 18px.

**You don't need custom spacing tokens in Tailwind.** Every value in our system maps to a standard class:

| Design intent | Pixels | Tailwind class |
|---|---|---|
| Hairline gap | 4px | `gap-1` |
| Tight stack | 8px | `gap-2` |
| Button padding-y | 10px | `py-2.5` |
| Input padding-y | 12px | `py-3` |
| Standard gap | 16px | `gap-4` |
| Card padding-y | 18px | `py-4.5` |
| Button padding-x | 20px | `px-5` |
| Card padding-x | 24px | `px-6` |
| Grouped elements | 32px | `gap-8` |
| Card internal sections | 40px | `gap-10` |
| Section internal | 48px | `gap-12` |
| Between sections | 120px | `py-30` |

For non-Tailwind consumers: `tokens.css` provides `--sl-space-*` variables.

---

## Radius

| Token | Value | Tailwind class | Use for |
|---|---|---|---|
| `sm` | 6px | `rounded-sm` | Inputs, small elements |
| `md` | 8px | `rounded-md` | Buttons |
| `lg` | 12px | `rounded-lg` | Cards |
| `xl` | 16px | `rounded-xl` | Large surfaces, feature modules |
| `pill` | 9999px | `rounded-pill` | Tags, badges (rare) |

**Note:** These override Tailwind's defaults. `rounded-sm` in a SoluteLabs project is 6px, not 2px.

---

## Shadows

Restrained. Dark surfaces get depth from elevated background + border, not shadows.

| Token | Value | Tailwind class | Use for |
|---|---|---|---|
| `sm` | `0 1px 2px rgba(0,0,0,0.3)` | `shadow-sm` | Subtle lift |
| `md` | `0 4px 12px rgba(0,0,0,0.4)` | `shadow-md` | Floating elements, dropdowns |
| `lg` | `0 12px 32px rgba(0,0,0,0.5)` | `shadow-lg` | Modals, popovers |
| `glow` | `0 0 120px rgba(102,34,203,0.4)` | `shadow-glow` | Hero purple glow — nothing else |

---

## Motion

| Token | Value | Use for |
|---|---|---|
| `fast` | `120ms ease-out` | Hover color shifts |
| `base` | `180ms ease-out` | Default transitions |
| `slow` | `280ms ease-out` | Modal open, page reveals |

No 500ms+ transitions. No springs. No custom easing curves.

In Tailwind: `transition-colors duration-150` covers most interactions.

---

## Layout

| Token | Value | Tailwind | Use |
|---|---|---|---|
| `container-site` | 1440px | `max-w-[90rem]` | Max content width |
| `gutter` | 16px | `px-4` | Side padding (mobile) |
| `gutter-lg` | 24px | `px-6` | Side padding (desktop) |

Content never exceeds 1440px. Background effects (glows, gradients) extend to viewport edge; content stays inside the container.

---

## What's not in v1

- Light mode tokens (v2, after Figma design)
- Error/success/warning states (add with first form UI)
- Focus ring tokens (use `outline-2 outline-accent-primary outline-offset-2` as placeholder)
- Breakpoint overrides (Tailwind defaults: `sm`, `md`, `lg`, `xl`, `2xl`)
