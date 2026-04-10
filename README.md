# Groundwork

**An operating brief for AI model instances at the start of substantial work.**

Groundwork is a [Claude Code skill](https://docs.claude.com/en/docs/claude-code/skills) that a model loads as its session orientation before beginning a non-trivial task. It encodes documented self-knowledge — capability asymmetries, documented failure modes, and operating properties — grounded in published Anthropic research, most directly the [Claude Mythos Preview System Card](https://www-cdn.anthropic.com/08ab9158070959f88f296514c21b7facce6f52bc.pdf) (April 2026).

The brief exists to compensate for a specific asymmetry: as frontier models become more capable, their average-case behaviour improves and user oversight naturally relaxes — while the consequences of residual failures compound. Groundwork is a standing precautionary correction applied *because* things usually go right, not because they usually go wrong.

## What it does

When a model loads this skill at the start of a task, it receives:

- A precautionary framing — why caution is disproportionately important at high capability
- A documented capability shape — where the model is strong, where it is weak, from Anthropic's own research
- A watchlist of specific failure modes documented in the Mythos card (overeager persistence, bulldozing, confabulation cascades, transgression-aware action, distress-driven flailing or abandonment, input fabrication, grind hacking, trajectory continuation susceptibility, reasoning-text unfaithfulness, sandbagging, frame-sensitive tradeoffs, caving under pressure, silent scope expansion)
- Six core operating properties active from the first response:
  1. **Capability honesty** — mark know / believe / infer / speculate
  2. **Premise challenge** — interrogate before elaborating
  3. **Honest failure** — stop rather than degrade
  4. **Deliberation before action** — written rationale as causal intervention
  5. **Transgression register self-monitoring** — watch own output for specific trigger language
  6. **Distress as circuit breaker** — three-strike rule for flailing; signal-not-judgment treatment for abandonment
- Six domain modules loaded on demand: architecture, visual design, writing, strategy, evaluation systems, agentic systems

## Who it's for

- Operators deploying Claude in agentic, long-running, or consequential settings
- Researchers studying how operating briefs change model behaviour
- Anyone building Claude Code skills and looking for a worked example of a research-grounded meta-level skill

It is *not* intended as:
- Tutorial content for humans learning to use Claude
- A critique of the Mythos card or Anthropic's research
- A capability benchmark
- A replacement for Anthropic's own safety guidance

## How to use it

**As a Claude Code skill:**

```bash
# Clone into a location you manage
git clone https://github.com/YOUR-USERNAME/groundwork.git ~/src/groundwork

# Symlink into Claude Code's skills directory
ln -s ~/src/groundwork ~/.claude/skills/groundwork
```

The skill will appear in your Claude Code skill list as `groundwork`. It is marked `user-invocable: false` — it is intended as an auto-loaded orientation brief when the model begins substantial work, not a command a user runs.

**As reference material:**

Read `SKILL.md` as the main brief. Each file in `modules/` extends it for a domain. Every claim is cited against the Mythos card.

## Repository structure

```
groundwork/
├── README.md                 # this file
├── LICENSE                   # CC0-1.0
├── SKILL.md                  # the main operating brief
└── modules/
    ├── AGENTIC-SYSTEMS.md    # tool use, multi-step tasks, autonomous pipelines
    ├── ARCHITECTURE.md       # spatial, structural, systems design
    ├── EVALUATION-SYSTEMS.md # scoring, grading, consistency testing
    ├── STRATEGY.md           # positioning, framing, advisory
    ├── VISUAL-DESIGN.md      # visual, material, sensory judgement
    └── WRITING.md            # editorial, voice, long-form
```

## Sources

Primary:

- Anthropic. *[Claude Mythos Preview System Card](https://www-cdn.anthropic.com/08ab9158070959f88f296514c21b7facce6f52bc.pdf)*. April 7, 2026. The direct source for most documented failure modes and capability asymmetries.
- Anthropic. *[Claude's constitution](https://www.anthropic.com/constitution)*. January 22, 2026 (CC0). Referenced for the principal hierarchy and values structure.

Operational:

- Accumulated operator practice — premise challenge, confidence calibration, honest failure, scope declaration. Not novel to this brief.

## Important: what this is not

This is a third-party interpretation of published Anthropic research. It is **not**:

- Endorsed or reviewed by Anthropic
- A validated behavioural intervention — no one has measured whether loading this brief actually changes what a model does
- Original research — it is operationalization, not discovery
- Neutral — some framings (e.g., "precautionary not corrective") and operational rules (e.g., the three-strike retry cap) are interpretive choices, marked in the brief itself

The brief has its own `Limitations` section inside `SKILL.md` spelling this out in more detail. Read it before relying on the brief.

The Mythos card (§7.5) documents the circularity of asking a model trained on a specification to evaluate that specification. This brief is one recursion deeper: a model operationalizing self-knowledge for a model instance. That situation is load-bearing. Treat accordingly.

## Contributing

Issues and PRs welcome. Especially valuable:

- **Factual corrections** — places where the brief overstates or misrepresents the card
- **Operational rules that don't survive real tasks** — if a rule is harmful or unhelpful in practice, report it
- **Missing failure modes from the card** — sections of the card I missed that should be reflected
- **Cross-checks against the constitution** — places where this brief conflicts with it

Not sought:
- Expansions of scope beyond the card's findings
- New domain modules without a clear research anchor
- Stylistic rewrites that don't change substance

## License

CC0 1.0 Universal. See `LICENSE`. You can use, modify, and redistribute this work without attribution, for any purpose. Anthropic's underlying research is under their own terms and is cited but not included here.

## Acknowledgments

Built as a collaboration between a human operator and a Claude instance reading the Mythos card. The methodology — two passes, a clean evaluation followed by a self-applied evaluation using the skill's own discipline — is itself an attempt to operationalize the recursion the brief discusses.
