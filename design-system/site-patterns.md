# Website Patterns (2026-08)

Patterns established during the August 2026 site redesign (homepage first fold →
/case-studies → /blog → article pages). These are decisions, not proposals — the
live site implements all of them. When building or reviewing a website surface,
follow this file alongside `components.md` and `tokens.md`.

## The dark first fold

Every redesigned first fold is a **flat dark band** — `surface-base` with the
dotted pixel field — not a purple gradient wash.

- Background: `bg-surface-base`, nothing else. The purple gradient hero images
  (`header-gradient*.webp`) are retired on redesigned folds.
- Texture: the dotted pixel field (below), faded at the band's edges with
  `h-28` top and `h-20` bottom gradients from/to `surface-base`.
- Headline: **left-aligned** on the content axis. Long titles are never
  centered — centered multi-line headlines force the eye to re-find each
  line's start. Title weight is regular–medium with looser leading (~1.25);
  ceremony comes from size and space, not boldness.
- Live examples: homepage hero, `/blog` masthead, blog article headers.
  (`/case-studies` keeps a gradient at reduced opacity under its dots — the
  one sanctioned exception, faded top and bottom so it reads as atmosphere.)

## The dotted pixel field

The homepage hero's dot grid is a brand texture, reused as a **static** field
on other surfaces (`StaticPixelField`, exported beside `HeroPixelField` in the
website repo).

- **Interactive** (idle wave + hover pixelate + click ripples): homepage hero
  only. One animated instance per site.
- **Static** (same grid at rest, drawn once, redrawn on resize only — no rAF
  loop, no listeners, renders under `prefers-reduced-motion`): every other
  sanctioned surface — hero bands, the pre-footer CTA band, 404, blog headers.
- Alpha: `0.07` at rest (the hero's value). Bump to ~`0.14` on bands whose
  content covers most of the field (the CTA/contact form band) — at 0.07 the
  dots vanish behind dense content.
- Ink: `foreground` on dark surfaces; pass the inverse token on light pages
  (404 uses `--color-foreground-inverse`).
- Do **not** put the field behind imagery-dense sections (card grids, logo
  walls, comparison tables) or article reading columns. It's an atmosphere for
  sparse dark bands; everywhere dilutes it.

## CTA hierarchy — exactly two tiers

1. **Convert** — solid white rectangle, dark text. Reserved for the single
   conversion action ("Talk to an Expert" in the nav / hero). Its power is
   scarcity: it must be the only white solid button in any viewport.
2. **Explore** — `RedirectionButton`: dark plate, 2px `edge-accent` (purple)
   left border, label + arrow, arrow nudges right on hover. Used for every
   section-level "go deeper" CTA (All Case Studies, View Clients, …).

No third button style. A section CTA must never dress like the conversion
button — visual similarity implies equal priority and dilutes the primary.

**Text links** inside content use white underline + arrow (the "Read case
study" / "Read article" affordance) — never orange. Orange (`accent-secondary`)
is a sparing highlight (stat digits, the accent underline, progress bar), never
a link or control color.

### The play control (case-study films)

White square plate with a play glyph that slides open to reveal "Watch the
video" — on card hover from `md` up, **always expanded below `md`** (no hover
on touch; a bare square doesn't read as a button). Placement: overlaid on the
still's bottom-left (the showcase's spot) or the card's eyebrow row — always a
real `<button>` outside any anchor. Opens the film in the shared `VimeoDialog`
lightbox.

## Navigation behavior

Smart reveal with hysteresis, sitewide:

- Hides on any downward scroll; stays visible in the top ~100px of the page.
- Reveals only after ~**80px of accumulated upward scroll**, so trackpad
  wobble and touch rubber-banding don't flash it mid-read.
- Anything else sticky on a page must clear the nav's height with its own
  top offset (the nav may return at any moment) — never reuse the nav's own
  show/hide machinery for other sticky elements.

## Article reading experience (/blog)

- **Measure**: body text capped at **70ch**. This outranks font-size — text on
  90+ character lines reads "small and dense" at any size.
- **Body**: `text-xl` desktop / `text-lg` mobile with ~1.6–1.65 leading. The
  site's fluid root (~13.5–16px across desktop widths) means nominal sizes
  render smaller than they read on paper — check rendered px, not class names.
- **Spacing**: paragraph gap ≥ `mb-5`; H2 gets `mt-12` desktop (a section
  break needs air above, roughly 2× the space below); H3 `mt-10` + a real
  bottom margin. Lists are `list-outside` with hanging indent and per-item gap.
- **Outline rail** (table of contents): scrollspy highlights the section being
  read; H3 sub-items appear **accordion-style under the active section only**.
  Active state = weight + brightness (medium weight, full white), inactive =
  light weight at 40% (sections) / 30% (subs) opacity. No accent color in the
  rail — the site's accents stay editorial, and the rail stays quiet.
- The reading column carries no texture, no decoration. Header band only.

## Naming

The blog is **LabNotes** — in the nav, the `/blog` masthead, article-page
rails, and the footer. One name everywhere; the URL stays `/blog`. "Insights"
and plain "Blog" as labels are retired.

## Card boundaries

The homepage case-study cards carry a full `edge` border on **mobile only**
(image + padded text inside one boundary, like the featured card); from `md`
up the border sits on the image alone. Don't introduce mixed treatments in one
grid — and when a card gains an interactive control, keep the text column's
geometry identical to its control-less siblings (no layout shift between
cards).
