# SoluteLabs Components (v1)

Three components: **Button**, **Card**, **Input**. Specs come from the Website-2025 Figma file. If something's missing, it doesn't exist yet.

All examples use the semantic token classes from `tailwind.css`. No raw hex values, no `text-white` — always the semantic utility.

---

## Button

Two variants. One shape.

### Primary

The solid white button. The most important action on screen. There should rarely be more than one visible at a time.

**Anatomy**

| Property | Token | Value |
|---|---|---|
| Background | `bg-white` (swappable via `--sl-btn-primary-bg` in v2) | `#FFFFFF` |
| Text | `text-foreground-inverse` | `#171717` |
| Border | none | — |
| Radius | `rounded-md` | 8px |
| Padding | `py-2.5 px-5` | 10px / 20px |
| Gap (icon to label) | `gap-2.5` | 10px |
| Font | Archivo Medium, `text-label` | 16px/16px |
| Letter spacing | `tracking-normal` | 0 |

**States**

| State | Treatment |
|---|---|
| Default | White background, charcoal text |
| Hover | `hover:bg-white/90` — `transition-colors duration-120` |
| Active | `active:bg-white/80` |
| Focus-visible | `outline-2 outline-accent-primary outline-offset-2` |
| Disabled | `opacity-40 cursor-not-allowed` — no hover response |

**Tailwind v4**

```jsx
<button className="inline-flex items-center gap-2.5 px-5 py-2.5 rounded-md
                   bg-white text-foreground-inverse
                   font-title font-medium text-label tracking-normal
                   transition-colors duration-120
                   hover:bg-white/90 active:bg-white/80
                   focus-visible:outline-2 focus-visible:outline-accent-primary
                   focus-visible:outline-offset-2
                   disabled:opacity-40 disabled:cursor-not-allowed">
  Talk to an Expert
</button>
```

**Why `bg-white` instead of a semantic token?** In dark mode, the primary button is literally white. In light mode, consider `bg-accent-primary` (purple) with `text-foreground-inverse` (white text) — this is a context decision per slide/page, not a token flip.

---

### Secondary

The outlined/ghost button. Supporting actions: "All Case Studies", "Explore More".

**Anatomy**

| Property | Token | Value |
|---|---|---|
| Background | transparent | — |
| Text | `text-foreground` | white |
| Border | `border border-edge` | 1px, white/15% |
| Radius | `rounded-md` | 8px |
| Padding | `py-4.5 px-8` | 18px / 32px |
| Gap (icon to label) | `gap-6` | 24px |
| Font | Archivo Medium, `text-body` | 18px/30px (intentionally larger than primary — secondary buttons have more padding and need visual weight) |
| Letter spacing | `tracking-normal` | 0 |

**States**

| State | Treatment |
|---|---|
| Default | Transparent, white text, standard edge border |
| Hover | `hover:bg-white/5 hover:border-edge-strong` |
| Active | `active:bg-white/[0.08]` |
| Focus-visible | Same outline as primary |
| Disabled | `opacity-40` |

**Tailwind v4**

```jsx
<button className="inline-flex items-center gap-6 px-8 py-4.5 rounded-md
                   bg-transparent text-foreground
                   font-title font-medium text-body tracking-normal
                   border border-edge
                   transition-colors duration-120
                   hover:bg-white/5 hover:border-edge-strong
                   focus-visible:outline-2 focus-visible:outline-accent-primary
                   focus-visible:outline-offset-2
                   disabled:opacity-40 disabled:cursor-not-allowed">
  All Case Studies
  <ArrowRight className="w-5 h-5" />
</button>
```

### Button rules

1. **One primary button per view.** If you think you need two, one is secondary.
2. **No "tertiary" variant.** Use a text link instead.
3. **Icons go right** for navigation (arrow), **left** for actions (back, add).
4. **No label animation.** Color/background transitions only.

### Text link (not a button)

- Color: `text-foreground`, underline offset `3px`, underline `rgba(255,255,255,0.3)`
- Hover: underline shifts to solid white
- Purple variant: `text-foreground-accent`, underline in purple-200

---

## Card

Dark background, restrained border, content. Used for case studies, features, stats.

**Anatomy**

| Property | Token | Value |
|---|---|---|
| Background | `bg-surface-raised` | `#1F1F1F` |
| Border | `border border-edge-subtle` | 1px, white/10% |
| Radius | `rounded-lg` | 12px |
| Padding | `py-4.5 px-6` | 18px / 24px |
| Internal section gap | `gap-10` | 40px |

**Structure**

Three optional zones, top to bottom:

1. **Media** — image, illustration, icon. Full-bleed if needed.
2. **Body** — title + description + optional list.
3. **Footer** — stats row, CTA, metadata.

No card requires all three. Stat card = body only. Case study = all three.

**Title typography**

```text
font-title font-medium text-title text-foreground tracking-tight
```

→ Archivo Medium, 24px/40px

**Description typography**

```text
font-body text-body text-foreground-muted tracking-wide
```

→ Manrope Regular, 18px/30px

**Highlighted variant** (featured/selected card)

- Border shifts to `border-edge-highlight` (orange)
- All other properties unchanged

**Tailwind v4**

```jsx
<article className="bg-surface-raised border border-edge-subtle rounded-lg
                    px-6 py-4.5 flex flex-col gap-10">
  <header className="flex flex-col gap-3">
    <h3 className="font-title font-medium text-title text-foreground tracking-tight">
      Full-Stack Migration
    </h3>
    <p className="font-body text-body text-foreground-muted tracking-wide">
      Legacy Angular app was blocking the product roadmap. We rebuilt the
      system using multi-agent workflows without slowing the team down.
    </p>
  </header>

  <ul className="flex flex-col gap-2 font-body text-body text-foreground-muted">
    <li>Angular 9 to modern stack</li>
    <li>Parallel frontend + backend execution</li>
    <li>No knowledge transfer required</li>
  </ul>

  <footer className="flex gap-8 pt-4.5 border-t border-edge-subtle">
    <div>
      <div className="font-title font-medium text-title text-foreground">
        22,000<span className="text-accent-secondary">+</span>
      </div>
      <div className="font-body text-label text-foreground-faint">LOC</div>
    </div>
  </footer>
</article>
```

### Card rules

1. **No drop shadows.** Depth = elevated background + border.
2. **Borders are subtle by default.** Only shift to `edge-strong` for interaction states.
3. **Stats inside cards use `font-title`** — they're mini-display text, not body.
4. **The `+` suffix uses `text-accent-secondary`** (bright-orange). `80%+`, `150+`, `22,000+`.

---

## Input

Form inputs for contact forms, newsletter signup, search.

> Note: No input appears on the current homepage. This spec is extrapolated from the system's existing patterns. Treat as a proposal until validated in Figma.

**Anatomy**

| Property | Token | Value |
|---|---|---|
| Background | `bg-surface-raised` | `#1F1F1F` |
| Text | `text-foreground` | white |
| Placeholder | `text-foreground-faint` | white/60% |
| Border | `border border-edge` | 1px, white/15% |
| Radius | `rounded-sm` | 6px |
| Padding | `py-3 px-4` | 12px / 16px |
| Font | Manrope Regular, `text-body` | 18px/30px |
| Min-height | `min-h-11` | 44px (touch target) |

**States**

| State | Treatment |
|---|---|
| Default | Raised bg, standard edge border |
| Hover | `hover:border-edge-strong` |
| Focus | `focus:border-edge-accent` (purple). No shadow, no extra outline |
| Error | Border `#EF4444` (not yet tokenized — v1.x addition) |
| Disabled | `opacity-40 cursor-not-allowed` |

**Label** — above input. Manrope Medium, `text-label`, `text-foreground`. Gap: `gap-2`.

**Helper/error text** — below input. Manrope Regular, `text-label`, `text-foreground-faint` (helper) or `#EF4444` (error).

**Tailwind v4**

```jsx
<div className="flex flex-col gap-2">
  <label className="font-body font-medium text-label text-foreground"
         htmlFor="email">
    Work email
  </label>
  <input
    id="email"
    type="email"
    placeholder="you@company.com"
    className="min-h-11 px-4 py-3 rounded-sm
               bg-surface-raised text-foreground
               placeholder:text-foreground-faint
               border border-edge
               font-body text-body tracking-wide
               transition-colors duration-120
               hover:border-edge-strong
               focus:border-edge-accent focus:outline-none
               disabled:opacity-40 disabled:cursor-not-allowed"
  />
  <span className="font-body text-label text-foreground-faint">
    We'll only use this to reply.
  </span>
</div>
```

### Input rules

1. **Never remove focus indication.** `focus:outline-none` is acceptable ONLY when paired with a visible border color change.
2. **Labels always above the input.** Never placeholder-only.
3. **No input shadows.** Flat + bordered.

---

## What's not in v1

- Dropdowns, selects, autocompletes
- Checkboxes, radios, toggles
- Navigation (header, footer, side nav)
- Tabs, accordions, modals
- Tables, data grids
- Toast, banner, alert
- Badges, tags, chips

Each gets added when the first real use case arrives.
