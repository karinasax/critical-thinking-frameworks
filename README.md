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
| **SIFT** (Mike Caulfield) | Fast fact-checking in four moves — Stop, Investigate the source, Find better coverage, Trace claims to origin — via lateral reading; the counter-discipline for verifying AI output | [frameworks/sift](frameworks/sift/) |
| **Life Reassessment** (Dan Koe) | Identity-first goal setting — excavate an anti-vision, orient toward a vision, and build a steerable plan through structured self-questioning | [frameworks/life-reassessment](frameworks/life-reassessment/) |

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

## Credits

Each framework is credited to its originators in its own entry. This collection
curates and adapts existing work; it does not claim authorship of the underlying
methods.

## License

Write-ups and curated content are licensed **CC BY 4.0**; the runnable skill code
under `frameworks/*/skill/` is licensed **MIT**. These cover only the repository
author's own contributions — the underlying methods remain the property of their
creators, as credited in each entry. See [LICENSE-NOTE.md](LICENSE-NOTE.md) for details.
