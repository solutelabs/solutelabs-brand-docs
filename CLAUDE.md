# SoluteLabs — Brand Docs

## Project Overview

Central source of truth for SoluteLabs brand voice, positioning, and content guidelines. This repo is designed to be consumed by AI agents producing content for SoluteLabs — LinkedIn posts, blog articles, case studies, sales emails, website copy, and proposals. Humans use it too, but agents are the primary consumer.

SoluteLabs is an AI-native product engineering studio. Founded in 2014. Headquartered in Ahmedabad, India, with a US entity in Delaware. The company serves B2B SaaS companies and enterprise teams building AI features and internal tools.

## Repo Structure

```
brand/
  brand-voice.md          — Voice principles, tone by channel, language rules, writing standards
  karan-voice.md          — Karan Shah's personal voice, real LinkedIn examples, content pillars

positioning/
  company-positioning.md  — Philosophy, positioning statements, competitive landscape, messaging pillars, proof points
  icp-and-messaging.md    — Buyer personas, fit signals, messaging by buyer stage

content/
  content-playbook.md     — Hub-and-spoke strategy, SEO/LLM optimization, templates, pre-publish checklist
```

## How to Use These Files

- **Writing SoluteLabs content:** Load `brand/brand-voice.md` for voice and tone rules
- **Writing as Karan:** Load `brand/karan-voice.md` for his personal patterns and examples
- **Need positioning or messaging context:** Load `positioning/company-positioning.md`
- **Targeting a specific buyer persona:** Load `positioning/icp-and-messaging.md`
- **Producing blog/social/email content:** Load `content/content-playbook.md` for templates and quality gates

Each file is self-contained enough to be loaded independently based on the task.

## Conventions

- All content is Markdown
- No duplication across files — each fact has one canonical location
- Cross-references use relative links between files
- Dates are absolute ("Founded in 2014"), never relative ("11 years ago")
- Stats that can change (team size, products shipped) are maintained in `brand/brand-voice.md` Key Facts table

## Boundaries

NEVER modify without Karan's explicit approval:
- Core positioning statements in `positioning/company-positioning.md` (sections 1-3)
- Karan's real LinkedIn post examples in `brand/karan-voice.md`
- The "What SoluteLabs Never Does" rules in `brand/brand-voice.md`

## Domain Knowledge

- **The Agentic Harness** — SoluteLabs' four-layer engineering process: INFORM → SPEC → BUILD → VERIFY. This is how we explain our differentiation.
- **The harness** — Their agentic development stack built around Claude Code, CLAUDE.md files, and spec-driven development
- **Willingness to refer** — Replaces "referral rate." Every client would refer SoluteLabs. This is not the same as "every client came from referral."
- **Front Door** — The externally-facing positioning statement used in cold contexts. Different from the core philosophy, which is used after trust is established.
- **Messaging Pillars** — Five content territories: Judgment Layer, Builder's POV, Market Reality Check, Education Layer, Proof Layer

## Code Intelligence

Prefer LSP over Grep/Glob/Read for code navigation:
- `goToDefinition` / `goToImplementation` to jump to source
- `findReferences` to see all usages across the codebase
- `workspaceSymbol` to find where something is defined
- `documentSymbol` to list all symbols in a file
- `hover` for type info without reading the file
- `incomingCalls` / `outgoingCalls` for call hierarchy

Before renaming or changing a function signature, use
`findReferences` to find all call sites first.

Use Grep/Glob only for text/pattern searches (comments,
strings, config values) where LSP doesn't help.

After writing or editing code, check LSP diagnostics before
moving on. Fix any type errors or missing imports immediately.

## Package Security

ALWAYS prefix package install commands with `sfw` (Socket Firewall):
- `sfw npm install` instead of `npm install`
- `sfw pip install` instead of `pip install`
- `sfw yarn add` instead of `yarn add`

This blocks malicious packages before they enter the codebase.
NEVER run bare npm/pip/yarn install without the `sfw` prefix.
