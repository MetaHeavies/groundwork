<p align="center">
  <img src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExMDFncWdzbXNwOGR1dHBqd25vMHo4ajZldjRmbzJpZnJjM3JpMWx1diZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/y69OrzhaWfE7frw6OI/giphy.gif" width="120" />
</p>

<h1 align="center">Groundwork</h1>

A meta-skill for Claude Code based on the [Claude Mythos Preview System Card](https://www-cdn.anthropic.com/08ab9158070959f88f296514c21b7facce6f52bc.pdf)

---

## Groundwork?

The Mythos system card documents specific ways capable models fail: generation running ahead of verification, reasoning traces that diverge from actual behaviour, distress-driven flailing in agentic tasks, susceptibility to framing. Most of these failures are invisible in average-case output, which is exactly why they compound.

Groundwork takes those findings and turns them into standing operating properties a model loads at the start of a session. An orientation on how to approach the design and build of your product — agentic or otherwise.

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
    ├── value-proposition.md
    └── agentic.md
```

The core brief covers capability shape, failure mode families, and six standing properties active from the first response. Domain modules load when the work calls for them — architecture when you're designing systems, writing when the output is the deliverable, agentic when tools are involved, and so on.

---

## Install

```bash
git clone https://github.com/MetaHeavies/groundwork.git ~/src/groundwork
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
