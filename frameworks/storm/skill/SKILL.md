---
name: storm
description: >-
  Run the Stanford STORM method — multi-perspective AI research that interrogates a topic
  from several expert viewpoints, maps where they contradict, synthesizes a briefing, then
  peer-reviews its own conclusions. Use this whenever the user wants to genuinely understand
  a topic rather than get a quick summary: before writing an article or report, making a
  business or investment decision, prepping for an interview or negotiation, evaluating a
  vendor or strategy, learning a new field, or building a presentation. Trigger it on
  "research X," "STORM," "I need to understand X deeply," "give me the full picture on X,"
  "what am I missing about X," "pressure-test this," or any request where a single-pass
  answer would miss blind spots, contradictions, or competing expert views. Reach for it
  even when the user doesn't say "STORM" — if they want depth, rigor, and a defensible
  conclusion rather than a surface take, this is the skill.
---

# STORM: Multi-Perspective Research

## What this does and why it works

A single question to an LLM returns the majority view — the most common framing, the surface. STORM (Synthesis of Topic Outlines through Retrieval and Multi-perspective Question asking, Stanford OVAL Lab, NAACL 2024) gets at real understanding by doing what a PhD researcher actually does: interrogate a topic from several distinct expert lenses, find where those experts *disagree* (that's where the real knowledge lives), pull it into a coherent briefing, then critique the briefing for bias and weak claims.

In Stanford's testing, multi-perspective articles were ~25% more organized and ~10% broader in coverage than single-prompt research. STORM's one acknowledged weakness is that it doesn't self-critique — source bias and fact misassociation slip through. Phase 4 exists specifically to fix that.

This skill runs that method as a **4-phase chain**, one phase at a time, pausing for the user between phases so they can steer.

## Before you start: gather two things

1. **The topic.** What exactly is being researched. If vague ("AI agents"), ask one quick question to sharpen it ("AI agents for what — a product decision, a market map, a technical build?").
2. **The user's role / decision context.** Phase 3 produces an action tailored to who the user is and what they're deciding. If it isn't obvious from the conversation, ask: "What will you do with this — and from what seat (founder, PM, investor, IC)?" This single input is what turns a generic briefing into something actionable.

Don't skip these. A sharp topic and a known decision context are what make the output worth the four phases.

## Adapting the personas

The default five lenses below work for most topics. But the *point* is diverse, genuinely-conflicting viewpoints — not these five exact labels. For a technical architecture question, "The Economist" and "The Historian" may add little, while "The Security Engineer" and "The Maintainer-in-2-years" would add a lot. For a clinical or legal topic, swap in the lenses domain experts would actually recognize.

**Rule of thumb:** keep the 4-phase structure rigid; adapt the persona set to the topic. Always include at least one lens whose job is to disagree with the others (the skeptic role), because the contradictions are the most valuable output. When you swap personas, briefly tell the user which lenses you chose and why before running Phase 1.

## The workflow

Run these **one phase at a time.** After each phase, show the output, then ask the user whether to continue, adjust, or stop. Keep all prior phases' output in context — each phase builds on the last. Don't auto-run all four; the pauses are where the user catches a wrong framing before it compounds.

Announce the plan first: "I'll run STORM in 4 phases — perspectives, contradictions, synthesis, peer review — pausing after each so you can steer."

---

### Phase 1 — The Multi-Perspective Scan

Generate the expert views. Use the default five unless you've adapted them for the topic (see above).

For each of the 5 perspectives, produce:
- **Core position** in 2 sentences
- **Strongest evidence** supporting their view
- **The one thing** they'd tell the user that no other perspective would

Default five lenses:
1. **The Practitioner** — works with this daily. What do they know that academics miss? What practical realities get ignored?
2. **The Academic** — has studied this for years. What does the peer-reviewed evidence actually say? Where does evidence contradict popular belief?
3. **The Skeptic** — thinks the mainstream view is wrong. What's the strongest counterargument? What evidence do proponents conveniently ignore?
4. **The Economist** — follows the money. Who profits from the current narrative? What financial incentives shape the research?
5. **The Historian** — has seen similar patterns before. What historical parallels exist? How did those play out?

Make the voices genuinely distinct — if they all sound the same, the method has failed. The practitioner should see what the academic misses; the skeptic should challenge what the practitioner assumes.

**Then pause.** Show the five views. Ask: continue to the contradiction map, adjust a persona, or stop?

---

### Phase 2 — The Contradiction Map

Now find where the voices fight. The disagreements are where understanding actually lives. Based on the perspectives from Phase 1:

1. **Direct contradictions** — where do two or more perspectives clash? List each conflict with the specific claims that collide.
2. **Evidence ranking** — which perspective has the strongest evidence? Which the weakest? Why?
3. **The resolving question** — what single question, if answered, would settle the biggest contradiction?
4. **Universal agreement** — what does *every* perspective agree on? This is likely true; even opponents confirm it.
5. **The blind spot** — what did *none* of the perspectives address? This is the gap in the whole field, and often the most valuable finding.

**Then pause.** Show the map. Ask: continue to synthesis, dig into one contradiction first, or stop?

---

### Phase 3 — The Synthesis

Pull everything into a research briefing. Use the topic and the user's role/decision context:

1. **One-paragraph summary** — explain the topic as if briefing a CEO who has 60 seconds and needs nuance, not just the headline.
2. **The 5 key findings** — most important things now known, *ranked by reliability*. For each, note which perspectives support it and which challenge it.
3. **The hidden connection** — one non-obvious link between findings that only appears when you look across all perspectives together.
4. **The actionable insight** — given the evidence, what should someone *in the user's specific role* actually do differently? Be concrete.
5. **The frontier question** — the one question that, if answered, would change how we understand this topic.

**Then pause.** Show the briefing. Ask: continue to peer review, or is this enough?

---

### Phase 4 — The Peer Review

This fixes STORM's known weakness: the method doesn't self-critique. Grade the briefing honestly.

1. **Confidence scores** — rate each of the 5 key findings 1–10 for reliability. Explain each score.
2. **Weakest link** — which claim are you least confident in? What specific information would verify it?
3. **Bias check** — which perspective is overrepresented in the synthesis? Did one voice dominate?
4. **Missing perspective** — is there a 6th lens that, if included, would change the conclusions?
5. **Overall grade** — if a domain expert reviewed this briefing, what grade would they give, and what would they tell the user to fix?

Be genuinely critical here — a peer review that finds nothing wrong isn't doing its job. If the bias check or missing-perspective step surfaces something material, offer to re-run Phase 1 with the corrected persona set.

---

## Output and follow-through

After Phase 4, give the user a short verdict: what's reliable, what to treat with caution, and the single most important next action for their role. If the peer review found a serious gap (a missing perspective that would change conclusions, or a dominant-voice bias), recommend a targeted re-run rather than presenting the briefing as final.

## When the user wants it fast

If the user explicitly asks to skip the pauses ("just run the whole thing," "don't stop between steps"), run all four phases in one pass and present the full chain. The default is to pause — but honor an explicit request for speed.

## Note on sources

The article this method comes from describes running it on the model's own knowledge. For higher-stakes research, strengthen it by giving each perspective real sources — use web search or provided documents so the evidence is grounded rather than recalled. Offer this when the topic is time-sensitive, factual, or consequential.
