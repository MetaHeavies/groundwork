# Groundwork

A meta-skill for Claude Code that loads before substantial work begins.

---

## Why it exists

Someone read the [Claude Mythos Preview System Card](https://www-cdn.anthropic.com/08ab9158070959f88f296514c21b7facce6f52bc.pdf) — Anthropic's most detailed public assessment of a frontier model to date — and applied it to their work. The results were good enough that I did the same thing, more systematically.

The card documents specific ways capable models fail: generation running ahead of verification, reasoning traces that diverge from actual behaviour, distress-driven flailing in agentic tasks, susceptibility to framing. Most of these failures are invisible in average-case output, which is exactly why they compound.

Groundwork takes those findings and turns them into standing operating properties a model loads at the start of a session. Not rules — orientation. The difference matters.

---

## What it is

A Claude Code skill with a core brief and six domain modules:

```
groundwork/
├── SKILL.md          ← core operating brief (always loads)
└── modules/
    ├── architecture.md
    ├── visual-design.md
    ├── writing.md
    ├── strategy.md
    ├── evaluation.md
    └── agentic.md
```

The core brief covers capability shape, failure mode families, and six standing properties active from the first response. Domain modules load when the work calls for them — architecture when you're designing systems, writing when the output is the deliverable, agentic when tools are involved, and so on.

---

## Install

```bash
git clone https://github.com/[your-handle]/groundwork.git ~/src/groundwork
ln -sf ~/src/groundwork ~/.claude/skills/groundwork
```

Personal install — available across all your projects. For a single project only, symlink into `.claude/skills/groundwork` at the project root instead.

To verify it loaded, start a new session and ask what skills are available. Groundwork should appear.

To update: `git -C ~/src/groundwork pull`

---

## What it is not

Not endorsed by Anthropic. Not validated against behavioural outcomes — the card shows deliberation reduces certain failure modes; it does not show this specific brief improves behaviour. Third-party operationalisation of published research.

---

## Source

Anthropic. *Claude Mythos Preview System Card*. April 7, 2026.
https://www-cdn.anthropic.com/08ab9158070959f88f296514c21b7facce6f52bc.pdf

Anthropic. *Claude's constitution*. January 2026.
https://www.anthropic.com/constitution
