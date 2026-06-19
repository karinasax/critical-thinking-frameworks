# STORM — Multi-Perspective Research

> **Synthesis of Topic Outlines through Retrieval and Multi-perspective Question asking**
> Stanford OVAL Lab · [NAACL 2024](https://arxiv.org/abs/2402.14207) · [github.com/stanford-oval/storm](https://github.com/stanford-oval/storm)

## The idea

A single question to an LLM returns the *majority view* — the most common framing, the
surface. STORM gets at real understanding by doing what a good researcher actually does:
interrogate a topic from several distinct expert lenses, find where those experts
**disagree** (that's where the real knowledge lives), pull it into a coherent briefing,
then critique that briefing for bias and weak claims.

In Stanford's evaluation, multi-perspective articles were ~25% more organized and ~10%
broader in coverage than single-prompt research. STORM's one acknowledged weakness is
that it doesn't self-critique — source bias and fact misassociation slip through. The
peer-review phase below exists specifically to patch that.

## When to use it

Reach for STORM when a single-pass answer would miss blind spots or competing expert
views — when you want to *genuinely understand* something rather than get a quick
summary:

- Before writing an article, report, or presentation
- Making a business, product, or investment decision
- Prepping for an interview, negotiation, or vendor evaluation
- Learning a new field from scratch
- Pressure-testing a position you already hold

## The protocol

Run as a **4-phase chain, one phase at a time**, pausing between phases so you can
steer. Keep every prior phase in context — each builds on the last. The pauses are
where you catch a wrong framing before it compounds.

First, gather two things: **a sharp topic** and **the decision context** (your role and
what you'll do with the answer). These are what turn a generic briefing into something
actionable.

### Phase 1 — The Multi-Perspective Scan

Generate distinct expert views. For each, produce a **core position** (2 sentences),
its **strongest evidence**, and **the one thing** that lens would say that no other
would.

Default five lenses (swap them to fit the topic — keep at least one skeptic):

1. **The Practitioner** — works with this daily; sees what academics miss.
2. **The Academic** — knows what the peer-reviewed evidence actually says.
3. **The Skeptic** — thinks the mainstream view is wrong; makes the strongest counterargument.
4. **The Economist** — follows the money and the incentives.
5. **The Historian** — has seen similar patterns before and how they played out.

The voices must be genuinely distinct. If they all sound the same, the method has failed.

### Phase 2 — The Contradiction Map

Find where the voices fight:

1. **Direct contradictions** — where do perspectives clash, on which specific claims?
2. **Evidence ranking** — strongest vs. weakest evidence, and why.
3. **The resolving question** — the single question that would settle the biggest conflict.
4. **Universal agreement** — what *every* lens agrees on (likely true).
5. **The blind spot** — what *none* of them addressed (often the most valuable finding).

### Phase 3 — The Synthesis

Pull it into a briefing, tailored to your role and decision:

1. **One-paragraph summary** — for someone with 60 seconds who needs nuance, not just the headline.
2. **5 key findings, ranked by reliability** — noting which lenses support and challenge each.
3. **The hidden connection** — a non-obvious link only visible across all perspectives.
4. **The actionable insight** — what someone *in your specific role* should do differently.
5. **The frontier question** — the one answer that would change the whole understanding.

### Phase 4 — The Peer Review

Patch STORM's known weakness — grade the briefing honestly:

1. **Confidence scores** — rate each finding 1–10 for reliability, with reasons.
2. **Weakest link** — the claim you're least sure of, and what would verify it.
3. **Bias check** — which perspective is overrepresented?
4. **Missing perspective** — a 6th lens that would change the conclusions?
5. **Overall grade** — what a domain expert would say to fix.

A peer review that finds nothing wrong isn't doing its job. If it surfaces a material
gap, re-run Phase 1 with the corrected persona set.

## Grounding the research

The base method runs on the model's own knowledge. For higher-stakes, time-sensitive, or
factual topics, strengthen it by giving each perspective **real sources** (web search or
provided documents) so the evidence is grounded rather than recalled.

## Runnable skill

This framework ships as a Claude skill in [`skill/`](skill/). Install it with:

```bash
cp -r skill ~/.claude/skills/storm
```

## Attribution

**The original method — STORM** was created by the **Stanford OVAL Lab**:

- Yijia Shao, Yucheng Jiang, Theodore A. Kanell, Peter Xu, Omar Khattab, Monica S. Lam,
  *Assisting in Writing Wikipedia-like Articles From Scratch with Large Language Models*,
  **NAACL 2024** — [arxiv.org/abs/2402.14207](https://arxiv.org/abs/2402.14207)
- Code (MIT license) & live demo: [github.com/stanford-oval/storm](https://github.com/stanford-oval/storm)
  · [storm.genie.stanford.edu](https://storm.genie.stanford.edu)

**The practical 4-prompt adaptation** that this entry's protocol and skill are based on
comes from **Nav Toor (@heynavtoor)**, *"The Stanford STORM Method: How to Make Claude
Research Like a PhD in Minutes"* (X, Jun 2026) —
[x.com/heynavtoor/status/2067194761446920264](https://x.com/heynavtoor/status/2067194761446920264).
The persona set, phase structure, and prompt wording here are adapted from that thread;
the skill extends it with phase-by-phase pausing, persona adaptation, and source-grounding
guidance.
