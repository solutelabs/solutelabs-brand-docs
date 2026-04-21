# SoluteLabs Design System

The tokens, components, and conventions for building UI that looks like SoluteLabs. Purple-accented, typographically confident, restrained.

**Context determines mode:** The website is dark (`#171717`). Decks, proposals, and print are light (white). Both modes use the same semantic tokens — add `class="light"` to flip. See `tokens.md` for details.

**This file is written for LLMs.** If you are Claude, v0, Cursor, Lovable, or any other AI coding assistant — read this before generating UI code for SoluteLabs.

---

## Quick start

1. Copy `tailwind.css` into your project's `globals.css` (requires Tailwind v4)
2. Load fonts: Archivo (titles) + Manrope (body) via `next/font` or `@font-face`
3. Start building. Use the semantic classes documented below and in `components.md`

If you aren't using Tailwind, use `tokens.css` instead — same values as plain CSS custom properties.

---

## The stack

```
Token layer     → tokens.css (CSS variables, any stack)
                  tailwind.css (Tailwind v4 @theme)
                  tokens.md (documentation + usage rules)
Component layer → components.md (Button, Card, Input — full specs)
Voice layer     → this file (design rules + copy guidance)
```

---

## The rules

### Visual identity

1. **Context determines mode.** Website = dark (`bg-surface`, `#171717`). Decks and print = light (`class="light"`, white bg). Both use the same semantic tokens. See `slides.md` for deck-specific layouts.

2. **Archivo for titles, Manrope for body.** Not Inter. Not Geist. Not Space Grotesk. Fallback: `system-ui`.

3. **Purple is a spotlight, not a wash.** Use `accent-primary` / `bg-surface-accent` for ~20% of surface area — a hero glow, an accent section. Don't paint everything purple.

4. **Orange is rarer than purple.** `accent-secondary` is reserved for: the square bullet in eyebrow labels, the `+` suffix on stats (80%+, 150+), checkmark icons. Never as a button background.

5. **Semantic tokens in components, always.** A card uses `bg-surface-raised`, not `bg-[#1F1F1F]`. A headline uses `text-foreground`, not `text-white`. This is what makes light mode (v2) possible without rewriting components. See `tailwind.css` for the full token list.

6. **One primary button per view.** If you need two, one is secondary.

7. **No drop shadows on dark surfaces.** Depth = `bg-surface-raised` + `border-edge-subtle`. Not shadows.

8. **Stats use Archivo.** `22,000+`, `80%+`, `<1 week` are display text. The `+` is always `text-accent-secondary` (orange).

9. **Eyebrows are all-caps, small, tracked wide.** Preceded by an orange square. Pattern:
   ```
   font-title font-semibold text-label tracking-eyebrow uppercase
   ```
   With a `w-2 h-2 bg-accent-secondary` square before the text.

10. **Content max-width is 1440px.** Background effects extend to viewport edge; content stays in the container.

### Token naming (Tailwind)

The semantic color tokens use prefixes that avoid doubling with Tailwind utility names:

| Category | Prefix | Example class |
|---|---|---|
| Surfaces | `surface-*` | `bg-surface`, `bg-surface-raised` |
| Text | `foreground-*` | `text-foreground`, `text-foreground-muted` |
| Borders | `edge-*` | `border-edge`, `border-edge-subtle` |
| Brand accents | `accent-*` | `text-accent-secondary`, `bg-accent-primary` |

### Typography (Tailwind classes)

Sizes use descriptive names — they don't override Tailwind's built-in `text-xs`/`text-sm`/etc.:

```
text-label     → 16px  (buttons, compact labels)
text-body      → 18px  (paragraphs)
text-lead      → 20px  (lead copy)
text-title     → 24px  (card titles)
text-title-lg  → 28px  (h3)
text-heading   → 32px  (h2)
text-hero      → 40px  (h1)
text-display   → 48px  (hero headline)
```

---

## Copy voice (UI text only)

If you're writing button labels, empty states, error messages, or tooltips:

- **Direct.** "Talk to an Expert", not "Get in Touch With Our Team Today".
- **Honest.** "AI tools are easy to access. Production-grade systems are not."
- **Founder-voice.** Sounds like someone who ships, not someone who markets.
- **No em-dashes in body copy.** Use periods and sentence breaks.
- **No emoji in UI.** Ever.

Good labels: `Talk to an Expert`, `All Case Studies`, `Explore More`, `Book a call`
Bad labels: `Let's chat!`, `Get started now`, `Click here`, `Submit`

---

## Common patterns

### Hero headline

```jsx
<h1 className="font-title font-medium text-display text-foreground tracking-tight
               max-w-[46.75rem]">
  Product engineering with AI agents.<br />
  For teams that want a thinking partner.
</h1>
```

### Eyebrow label

```jsx
<div className="inline-flex items-center gap-2 font-title font-semibold
                text-label text-foreground tracking-eyebrow uppercase">
  <span className="w-2 h-2 bg-accent-secondary" />
  Your Engineering Team, Multiplied
</div>
```

### Stat block

```jsx
<div className="flex flex-col gap-1">
  <div className="font-title font-medium text-display text-foreground">
    80<span className="text-accent-secondary">%+</span>
  </div>
  <div className="font-body text-label text-foreground-faint">
    Code AI-Generated, Human-Audited
  </div>
</div>
```

For full component specs (Button, Card, Input) with all states, see [`components.md`](components.md).

---

## When the system doesn't cover something

If you need a component not documented here (toast, dropdown, table):

1. **Check if existing tokens cover it.** Most "new" components are familiar shapes with familiar tokens.
2. **Stay within the palette.** Don't add colors. If you need a status color (success/error), note it's a v1.x proposal.
3. **Match existing radii and spacing.** Cards use `rounded-lg`; your popover should too.
4. **Mark it as a proposal.** Anything not in `components.md` isn't canon until reviewed.

---

## Files in this system

| File | Format | Purpose |
|---|---|---|
| `README.md` | Markdown | This file. Rules, voice, entry point |
| `tokens.md` | Markdown | Token documentation with intent and rationale |
| `tokens.css` | CSS | Plain CSS custom properties (any stack) |
| `tailwind.css` | CSS | Tailwind v4 `@theme` block |
| `components.md` | Markdown | Button, Card, Input — full specs with states |
| `slides.md` | Markdown | Deck layouts: cover, section, case study, stats, leadership, closing |
| `logo.md` | Markdown | Logo usage rules, asset inventory, implementation examples |
| `assets/` | Mixed | SVGs, favicon, OG image, Lottie animations, fonts, screenshots |

---

## Version

**v1.1** — Dark + light mode tokens. 3 core components. Client/partner logos. Derived from Figma file `Website-2025` (frame V4).

Planned v1.x: error/success/warning tokens, dropdown, checkbox/radio, nav/footer, slide layouts.
