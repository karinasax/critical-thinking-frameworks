# Critical Thinking Frameworks

A curated, researched collection of frameworks, methods, and protocols for thinking
more clearly — and for getting genuinely better answers out of AI rather than fast,
shallow ones.

Each entry aims to capture not just *what* the framework is, but **when to reach for
it**, **how to actually run it**, and **where it comes from**. Where a framework has
been turned into a runnable [Claude skill](https://docs.claude.com/en/docs/claude-code/skills),
the skill files are committed alongside the write-up so it can be installed and used
directly.

## Frameworks

| Framework | What it's for | Entry |
|-----------|---------------|-------|
| **STORM** (Stanford OVAL) | Multi-perspective research — interrogate a topic from several expert lenses, map their contradictions, synthesize a briefing, then peer-review it | [frameworks/storm](frameworks/storm/) |

*More entries coming — this is an evolving collection.*

## How entries are structured

Each framework lives in `frameworks/<name>/`:

- **`README.md`** — the write-up: what it is, when to use it, the protocol/prompts, and the source.
- **`skill/`** *(when available)* — the runnable Claude skill (`SKILL.md` and any supporting files).

## Using the skills

To install a framework that ships as a Claude skill, copy its `skill/` directory into
your skills folder:

```bash
cp -r frameworks/storm/skill ~/.claude/skills/storm
```

Then invoke it in Claude Code (e.g. `/storm`) or just describe the kind of thinking you
want — a well-written skill triggers on intent, not only on its name.

## Contributing

This started as a personal research project. Suggestions for frameworks worth adding —
especially with a good primary source — are welcome via issues or PRs.
