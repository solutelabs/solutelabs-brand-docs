# Content Playbook

How to plan, structure, and produce content for SoluteLabs — optimized for Google ranking, LLM citation, and buyer conversion. This is the primary reference for AI agents producing SoluteLabs content.

---

## Hub and Spoke Model

Structure all content using a hub-and-spoke model. Each messaging pillar (see [Company Positioning](../positioning/company-positioning.md#8-messaging-pillars)) can generate one or more **hub pages** — comprehensive, authoritative pieces that own a broad topic. **Spoke pages** are specific, detailed posts that link back to the hub and target long-tail queries.

### How It Works

- **Hub pages** are evergreen, comprehensive guides (2,000–4,000 words). They target a primary keyword cluster and serve as the authoritative page for that topic.
- **Spoke pages** are focused posts (800–2,000 words) that go deep on a subtopic. Every spoke links back to its hub. Every hub links out to its spokes.
- Hubs should be updated as new spokes are published — they're living pages, not static posts.
- Internal linking between spokes across pillars is encouraged when the connection is natural.

### Example — Pillar 2 (Builder's POV)

- **Hub:** "How We Build AI Products — Our Gen 3 Engineering Process"
- **Spokes:**
  - "We built three RAG systems last quarter — here's how we decide architecture"
  - "ElevenLabs in production — what the docs don't tell you"
  - "Angular 9 to Next.js: 22K lines in under a week"
  - "Building internal tools for a 600-vessel fleet (Synergy Marine)"

### Example — Pillar 4 (Education Layer)

- **Hub:** "How to Evaluate an AI Development Partner"
- **Spokes:**
  - "Questions to ask any AI development partner before signing"
  - "What a production-ready AI build actually costs"
  - "How to scope an AI MVP without wasting your first three months"

---

## SEO & LLM Optimization

### For Google

- Each hub targets a primary keyword cluster. Spokes target specific long-tail variations.
- First paragraph of any page should be a concise, self-contained summary — this is what Google pulls for featured snippets.
- Use primary keywords naturally in the first 100 words, H1, and at least one H2.
- Internal links: minimum 3–4 per post to other SoluteLabs pages.
- External links: high-authority, relevant sources only.
- Meta title: under 60 characters. Meta description: under 160 characters.

### For LLM Citation

LLMs pull from content that is structured, factual, and extractable. To increase the chance of being cited:

- Include clear, standalone factual statements. Example: "SoluteLabs deploys multi-agent AI systems using spec-driven development, Claude Code, and parallel subagent execution."
- Use structured formats (tables, numbered lists, definition-style paragraphs) that LLMs can extract cleanly.
- Answer the question the reader is asking in the first paragraph — don't bury it.
- Name specific tools, frameworks, and methodologies. Vague language gets skipped by LLMs.

---

## Content Types by Funnel Stage

| Funnel Stage | Content Type | Pillar Fit | Goal |
|---|---|---|---|
| Top (Unaware) | LinkedIn posts, blog thought pieces, market takes | Pillars 3, 4 | Create awareness, earn the click |
| Middle (Exploring) | Technical blogs, architecture breakdowns, comparison guides | Pillars 1, 2 | Build credibility, demonstrate judgment |
| Bottom (Evaluating) | Case studies, proof points, "how we work" pages | Pillars 2, 5 | Win trust, remove risk |

See [ICP & Messaging](../positioning/icp-and-messaging.md) for stage-specific messaging.

---

## Karan's Content vs. Company Content

| | Company Content | Karan's Content |
|---|---|---|
| **Voice** | "We" — the studio | "I" — the founder |
| **Purpose** | Authority, SEO, lead gen | Trust, reach, personal connection |
| **Where** | Blog, website, company social | LinkedIn, talks, podcasts |
| **Pillar overlap** | All five | Primarily Pillars 1, 2, 3 |

See [Karan's Voice](../brand/karan-voice.md) for his content pillars, voice guidelines, and real post examples.

---

## Templates

### Blog Post

```
# [Title — clear, specific, benefit-oriented]

[Opening hook — 1-2 sentences that name the problem or tension]

[Context — why this matters now]

## [Section 1 heading]
[Body]

## [Section 2 heading]
[Body]

## [Section 3 heading]
[Body]

## Key takeaway
[1-2 sentence summary of the main point]

## CTA
[What should the reader do next?]
```

### Case Study

```
# [Client name]: [Result in one line]

## The challenge
[What problem did the client face? What had they tried?]

## Why SoluteLabs
[Why did they choose us? What was the selection criteria?]

## What we built
[Solution overview — tech stack, approach, timeline]

## Results
[Quantified outcomes — metrics, before/after, quotes]

## Tech stack
[Bullet list of technologies used]
```

### LinkedIn Post (Karan)

Karan's posts follow a few recurring structures. Pick the one that fits. See [Karan's Voice](../brand/karan-voice.md) for full examples and writing patterns.

#### Structure A — Nuanced take (most common)

```
[Story or anecdote — specific person, place, moment]

[Quote or surprising claim]

[Counterpoint — "But..."]

[Reframe — "So who's right? Both." / "The real question is..."]

[Parallel structure landing the point]
[Line 1 — for X.]
[Line 2 — for Y.]

[One-line closer that reframes the question]

[Hashtags — 3-5]
```

#### Structure B — Build in public

```
[What I did — specific, one line]

[The problem I was solving]

[What I built / how it works — name the tools]

[The result — contrast with old way]

[Broader insight — why this matters beyond me]

[Self-aware caveat — "I'm not saying this to flex..."]

[One-line closer]
```

#### Structure C — Hiring / team

```
[Role. Location. One line.]

[The job in one line — framed as a standard, not a description]

[Context — who we are, what we've done]

[What I need — arrow list (→)]

[Requirements — short, specific]

[CTA that doubles as the filter]
```

#### Structure D — Personal / reflective

```
[Surprising or contrarian opening line]

[Personal story or admission]

[Broader insight about founders / entrepreneurship / culture]

[Warm closer — question or reflection]

[Hashtags]
```

### Sales Email (Cold Outreach)

```
Subject: [Short, specific, no clickbait]

[Personalized opener — reference something specific about them]

[One sentence on the problem we solve]

[One proof point — result, client, or insight]

[Soft CTA — question, not a demand]
```

### Social Media Post (Company)

```
[Hook — first line matters most]

[Core message — 2-3 lines max]

[CTA or engagement prompt]

[Hashtags if applicable]
```

---

## Pre-Publish Checklist

Before publishing any piece of content, run it through these six tests. If it fails more than one, revise before publishing.

### Test 1 — The Judgment Test
> Does this content demonstrate business judgment, not just technical capability?

SoluteLabs is not a coding shop. Our best content reflects the thinking that goes into what we build, not just how we build it. If the content reads like a tutorial or a feature showcase without any "here's why we made this decision" layer, add it.

### Test 2 — The Specificity Test
> Is there at least one specific, concrete detail — a real number, a named tool, a real project outcome?

Generic claims destroy credibility with our buyers. "We build AI products fast" is worthless. "We rebuilt an Angular 9 codebase into Next.js — 22,000 lines of code — in under a week, using multi-agent orchestration with Claude Code" is credible. Every piece of content needs at least one anchor to reality.

### Test 3 — The ICP Test
> Would a CTO, technical founder, or business owner with domain expertise find this immediately useful or credible?

If the answer is "a general AI enthusiast would like this" — revise. We are not writing for the AI Twitter crowd. We are writing for people making real product and technology decisions. If it doesn't speak to a real decision they face, it's not for us.

### Test 4 — The Differentiation Test
> Does this reinforce something that SoluteLabs uniquely stands for?

If a generic AI agency could have published this exact piece of content — the judgment layer is missing. Ask: what's the SoluteLabs POV here? What have we learned from actually building this? What would we tell a client that they probably won't hear from anyone else?

### Test 5 — The "Are We Selling or Helping?" Test
> Does this content try to help the reader first, or sell SoluteLabs first?

Our content should make the reader smarter, more informed, or better equipped to make a decision — regardless of whether they hire us. Content that leads with helpfulness builds trust. Content that leads with selling builds resistance. We always lead with helpfulness. The pitch, if present at all, is at the end and is light.

### Test 6 — The Stranger Test
> Would someone who has never heard of SoluteLabs stop, read this, and find it immediately relevant to a problem they're feeling right now?

If the content only resonates once you already know and trust SoluteLabs — it's doing Layer 2 work. That's valuable, but you also need content that pulls strangers in. Layer 2 content builds trust with people already in your orbit. Layer 1 content grows the orbit.

Ask: does this lead with a specific, felt problem — or does it lead with our philosophy and proof points? Philosophy and proof points belong in the body and close, not the hook.

**The target ratio:** At least one in every four pieces of content should pass this test — leading with a problem the reader recognises before they've heard of us.
