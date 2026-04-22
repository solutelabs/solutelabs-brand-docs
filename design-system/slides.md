# SoluteLabs Slide Layouts

Layout templates for decks and presentations. Based on the current Pitch deck with design improvements documented here.

**Mode:** Light. Decks use `class="light"` — white backgrounds, charcoal text. The website is dark; decks are not.

**Reference screenshots:** `assets/screenshots/deck-*.png`

---

## Slide types

The deck uses 8 slide types. Every slide in a SoluteLabs deck is one of these.

| Type | Background | When to use |
|---|---|---|
| Cover | Purple (`#6622CB`) | First slide only |
| Section divider | Charcoal (`#171717`) | Before each major section |
| About / Stats | White | Company facts, metrics |
| Content (two-column) | White | Capabilities, features, comparisons |
| Logo wall | White | Client logos, grouped by category |
| Case study | White | Client work with stats + testimonial |
| Leadership | White | Team bios |
| Closing | White + charcoal panel | Last slide, contact info |

---

## Cover slide

Purple background. The only slide where purple is a full surface.

**Layout:**

```text
┌─────────────────────────────────────────────────┐
│                                                 │
│  [Logo wordmark — white]                        │
│                                                 │
│                                                 │
│  Your Engineering Team,                         │
│  Multiplied                    (italic)         │
│                                                 │
│  [Partner badges — row]                         │
│                                                 │
│                                                 │
│                              [Icon mark — white]│
│  © 2014-2026 SoluteLabs                         │
└─────────────────────────────────────────────────┘
```

**Rules:**

- Headline is italic (Archivo Medium Italic, `text-display`)
- No orange dot or decorative elements on the headline
- No animated title reveal — static text
- Partner badges in white-background pills, bottom-left
- Icon mark (flat, white) as decorative element, bottom-right
- Copyright line, bottom-left, muted

---

## Section divider slide

Charcoal background (`#171717`). Used to introduce major sections: "Case Studies", "Our Process", "Leadership".

**Layout:**

```text
┌─────────────────────────────────────────────────┐
│                                                 │
│                                                 │
│                                                 │
│  Section Title                                  │
│                                                 │
│                                                 │
│                                                 │
│                              [Icon mark — white]│
└─────────────────────────────────────────────────┘
```

**Rules:**

- Headline: Archivo Medium, `text-hero` or `text-display`, white
- No subtitle needed — the section title is enough
- Icon mark bottom-right (optional)
- No other elements

---

## About / Stats slide

White background. Company overview with stacked or horizontal stats.

**Layout (horizontal stats):**

```text
┌─────────────────────────────────────────────────┐
│                                                 │
│  Headline                                       │
│  [Body text — one or two lines]                 │
│                                                 │
│                                                 │
│  ┌──────────┬──────────┬──────────┐             │
│  │  2014    │  150+    │  4.7★    │             │
│  │  Founded │  Products│  Clutch  │             │
│  │  DE, USA │  shipped │  rating  │             │
│  └──────────┴──────────┴──────────┘             │
│                                                 │
│                                    [Icon mark]  │
└─────────────────────────────────────────────────┘
```

**Rules:**

- Stats use Archivo Medium, `text-heading` or `text-hero` size
- Stat labels use Manrope, `text-body`, `text-foreground-muted`
- Stats separated by purple vertical dividers
- Maximum 3-4 stats per row
- The `+` suffix on numbers uses `text-accent-secondary` (orange)
- No team headcount stat (brand rule)

---

## Content slide (two-column)

White background. For capabilities, service lists, comparisons.

**Layout:**

```text
┌─────────────────────────────────────────────────┐
│                                                 │
│  Headline                                       │
│                                                 │
│  ┌─────────────────┐ │ ┌─────────────────┐      │
│  │ Column Title    │ │ │ Column Title    │      │
│  │                 │ │ │                 │      │
│  │ • Item one      │ │ │ • Item one      │      │
│  │ • Item two      │ │ │ • Item two      │      │
│  │ • Item three    │ │ │ • Item three    │      │
│  │                 │ │ │ • Item four     │      │
│  └─────────────────┘ │ └─────────────────┘      │
│                      │                          │
│                                    [Icon mark]  │
└─────────────────────────────────────────────────┘
```

**Rules:**

- Purple vertical bar separates columns (not a full border — just a line)
- Column titles: Archivo Medium, `text-title`, with short purple underline below (these are sub-headers, not links)
- List items: Manrope Regular, `text-body`
- Bullet points: purple checkmarks for feature lists, plain text for simple lists
- No more than two columns

---

## Logo wall slide

White background. Client logos grouped by category.

**Layout:**

```text
┌─────────────────────────────────────────────────┐
│                                                 │
│  Clients                                        │
│                                                 │
│  Enterprises        SMEs           Startups     │
│  ┌───┐ ┌───┐      ┌───┐ ┌───┐    ┌───┐ ┌───┐  │
│  │   │ │   │      │   │ │   │    │   │ │   │  │
│  └───┘ └───┘      └───┘ └───┘    └───┘ └───┘  │
│  ┌───┐ ┌───┐      ┌───┐ ┌───┐    ┌───┐ ┌───┐  │
│  │   │ │   │      │   │ │   │    │   │ │   │  │
│  └───┘ └───┘      └───┘ └───┘    └───┘ └───┘  │
│                                                 │
│                              Complete list →    │
└─────────────────────────────────────────────────┘
```

**Rules:**

- Three columns: Enterprises, SMEs, Startups (or by industry: Healthcare, Finance, Media, etc.)
- Column headers: Archivo Medium, `text-title`, `text-foreground`
- Logos in original colors, sized to fit a consistent bounding box (~120px wide)
- 2-3 rows per column, 2-3 logos per row
- "Complete list" link bottom-right (purple, links to solutelabs.com/clients)
- Client logos are in `assets/logos/clients/`
- Use standard (colored) variants on white slides, `trusted-*` (white) variants on dark slides

---

## Case study slide

White background. The most common slide type. Shows client work with proof points.

**Layout:**

```text
┌─────────────────────────────────────────────────┐
│                                                 │
│  Headline for the                [Client logo]  │
│  Case Study                                     │
│  [Link to full case study]                      │
│                                                 │
│  ✓ Bullet point one    ✓ Bullet point three     │
│  ✓ Bullet point two    ✓ Bullet point four      │
│                                                 │
│  ┌────────┬────────┬────────┐  ┌──────────────┐ │
│  │ Stat 1 │ Stat 2 │ Stat 3 │  │ [Screenshot] │ │
│  │ label  │ label  │ label  │  │              │ │
│  └────────┴────────┴────────┘  │              │ │
│                                │  "Quote..."  │ │
│  [Tech stack icons — row]      │  — Name      │ │
│                                │    Title      │ │
│                                └──────────────┘ │
└─────────────────────────────────────────────────┘
```

**Rules:**

- Headline: Archivo Medium, `text-heading`. Key product/outcome word can be bold
- No underlines on headlines (deck context — nothing is clickable in a presentation)
- Client logo: top-right corner, original colors
- Bullet points: purple checkmarks (not grey, not orange)
- Stats row: Archivo Medium for numbers, Manrope for labels, purple dividers between stats
- The `+` suffix uses orange (`text-accent-secondary`)
- Screenshot or product image: right side, with subtle border
- Testimonial quote: below or beside screenshot, with headshot, name, title
- Tech stack icons: bottom-left row, original logo colors, small
- "Read our Clutch feedback" link: purple, below testimonial (this IS a link in shared decks)

---

## Leadership slide

White background. Team bios.

**Layout:**

```text
┌─────────────────────────────────────────────────┐
│                                                 │
│  Leadership                                     │
│                                                 │
│  ┌──────────────────┐  ┌──────────────────┐     │
│  │   [Photo]        │  │   [Photo]        │     │
│  │   (circle,       │  │   (circle,       │     │
│  │    orange border)│  │    orange border) │     │
│  │                  │  │                  │     │
│  │  Name            │  │  Name            │     │
│  │  Title           │  │  Title           │     │
│  │  [LinkedIn icon] │  │  [LinkedIn icon] │     │
│  │                  │  │                  │     │
│  │  Bio text...     │  │  Bio text...     │     │
│  │                  │  │                  │     │
│  │  Schedule a call │  │  Schedule a call │     │
│  └──────────────────┘  └──────────────────┘     │
│                                                 │
└─────────────────────────────────────────────────┘
```

**Rules:**

- Headshots: circular crop with orange (`#FF4D00`) border ring — this is the one place orange appears prominently outside stats
- Name: Archivo Medium, `text-title`
- Title: Manrope, `text-body`, muted
- Bio: Manrope, `text-body`, 3-4 lines max
- "Schedule a call" link: purple
- Maximum 2-3 people per slide

---

## Closing slide

White left panel + charcoal right panel with silhouette photo.

**Layout:**

```text
┌──────────────────────────┬──────────────────────┐
│                          │                      │
│  "Stay Curious"          │                      │
│  (handwritten script)    │  [Icon mark]         │
│                          │                      │
│  Website: url            │                      │
│  Email: email            │  [Silhouette photo]  │
│                          │                      │
│  [Clutch badge]          │                      │
│  Social links            │                      │
│                          │                      │
│  Get in touch            │                      │
│  HQ address | US address │                      │
│  Phone      | Phone      │                      │
│                          │                      │
│  © 2014-2026 SoluteLabs  │                      │
└──────────────────────────┴──────────────────────┘
```

**Rules:**

- "Stay Curious" is a handwritten/script element — brand sign-off
- Left panel: white, all contact info
- Right panel: charcoal, icon mark top, atmospheric silhouette photo
- Clutch badge: small, near the social links
- Two-column address layout: HQ (India) and Delivery Centre / US entity

---

## Global deck rules

### Backgrounds

- **Purple** — cover slide only
- **Charcoal** — section dividers and closing panel only
- **White** — everything else

### Typography

- **Headlines:** Archivo Medium (or Medium Italic on cover), `tracking-tight`
- **Body:** Manrope Regular, `tracking-wide`
- **Stats:** Archivo Medium, large. The `+` suffix in orange
- **Labels/captions:** Manrope, muted color

### Accent usage

- **Purple checkmarks** — bullet points on content/case study slides
- **Purple vertical bars** — column dividers, stat dividers
- **Purple horizontal rules** — between stacked stat blocks
- **Orange square** (`▪`) — eyebrow labels only (rare in decks)
- **Orange `+`** — stat suffixes only
- **Orange circle border** — leadership headshot frames only

### What NOT to do

- No underlines on headlines (underlines are for web links, not deck emphasis)
- No animated title reveals (static text is clearer)
- No video embeds (won't play in presentations — use screenshots)
- No gradient backgrounds (flat surfaces only)
- No drop shadows on any element
- No team headcount stats
- No orange dot decoration next to headlines
- No emoji

### Persistent elements

- Icon mark: bottom-right on white slides (in purple circle, subtle)
- Copyright: bottom-left, `text-foreground-faint`
- No logo wordmark on content slides (only on cover and closing)

---

## Deck structure (recommended order)

1. **Cover** (purple) — tagline + partner badges
2. **About** — company overview + key stats
3. **Capabilities** — two-column service list
4. **How We Build** — Agentic Harness process
5. **Section: Case Studies** (charcoal divider)
6. **Case study slides** (3-5, tailored to prospect's industry)
7. **Clients** — logo wall
8. **Section: Team** (charcoal divider)
9. **Leadership** — founder bios
10. **Closing** — contact info + "Stay Curious"
