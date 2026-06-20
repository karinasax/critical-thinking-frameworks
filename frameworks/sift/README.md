# SIFT — Fact-Checking in Four Moves

> **Stop · Investigate the source · Find better coverage · Trace claims to the original context**
> Mike Caulfield · [hapgood.us/2019/06/19/sift-the-four-moves](https://hapgood.us/2019/06/19/sift-the-four-moves/)
> Originally *"Four Moves and a Habit"* in *Web Literacy for Student Fact-Checkers* (2017)

## The idea

Most "evaluate your sources" advice tells you to read *down* a page — scrutinise the
author bio, the about page, the design, the citations. Misinformation is good at all of
those. SIFT does the opposite: it gets you **off the page fast** to check what the rest
of the web says, decide in seconds whether something is worth your attention, and trace
claims back to where they actually came from. The core habit underneath all four moves
is **lateral reading** — leaving a source to find out what *others* say about it, rather
than trusting what it says about itself.

It replaced checklist methods like CRAAP across hundreds of universities because
checklists reward surface signals (looks professional, has references) that bad sources
imitate easily — whereas lateral reading checks the one thing they can't fake: their
reputation among people who'd know.

## Why it matters for AI

A language model is the ultimate page that reads well. Caulfield calls AI output an
**"information smoothie"** — fluent, confident, easy to drink, and impossible to trace
to its ingredients. The blend dissolves exactly the provenance SIFT was built to recover.
His reframing: treat AI as **"a portal, not a portrait"** — not a thing to read and
believe, but a way to *get to* sources you then verify yourself.

SIFT is the natural counter-discipline. When a model hands you a claim, a quote, a
statistic, or a citation, the four moves tell you what to do before you believe it — and
the *Trace* move catches the failure case unique to AI: confident claims with fabricated
or misattributed sources.

## When to use it

Reach for SIFT in seconds, many times a day — it's a fast triage habit, not a research
project:

- A claim, statistic, quote, or "study says…" from an AI, a link, or a feed
- A citation or source an AI offered — *before* you repeat or rely on it
- Anything that triggers a strong emotional reaction (the trigger for **Stop**)
- Deciding whether a source is even worth your time to read closely
- Vetting a screenshot, image, or out-of-context video

For deep, multi-perspective research rather than fast verification, reach for
[STORM](../storm/) instead — SIFT checks *whether to trust a claim*; STORM
*builds understanding across competing views*.

## The four moves

You don't run these in strict order — you reach for the move that fits. But **Stop** is
always first and last.

### S — Stop

Before reading, sharing, or acting: pause. Notice your emotional reaction (outrage and
delight are both manipulation surfaces). Ask what you already know about the source and
the claim. And — crucially — *re-Stop* whenever you get lost: if you're an hour deep and
spun up, return to your purpose. How much effort a claim deserves depends on what you'll
do with it.

### I — Investigate the source

Know what you're reading **before** you read it — not by trusting the source's own
about-page, but by reading laterally: open new tabs, see what independent sources say
about this author/publication/account. Thirty seconds of "who is this and why should I
listen" reframes everything that follows. *Expertise and agenda, not just existence.*

### F — Find better coverage

Often you don't care about *this* source — you care about the *claim*. Leave it and look
for the best coverage you can find: do trusted outlets, fact-checkers, or domain experts
corroborate, contradict, or add context? Look for the **consensus of reporting**, not a
single confirming hit (which you can always find).

### T — Trace claims, quotes, and media to the original context

Re-reported claims get stripped of context, cherry-picked, or quietly distorted. Follow
the chain back: find the original study, the full quote, the uncropped image, the primary
document. Check whether the original actually says what the secondhand version claims.
**This is the move that catches AI fabrication** — when you trace a model's citation and
the source doesn't exist, doesn't say that, or doesn't exist *yet*.

## Applying SIFT to AI output

Caulfield's adaptation of the habit for working with language models — three moves layered
on top of the four:

1. **Get it in** — bring the actual source material *into* the model (paste the document,
   give it the link, attach the file) rather than asking it to recall. Recall is the
   smoothie; grounding it in real text is how you get a portal instead.
2. **Track it down** — when the model makes a claim, make it produce the source, then go
   *Trace* it. Don't accept a citation you haven't opened. A plausible-looking reference is
   the single most common AI failure mode.
3. **Follow up** — interrogate. Ask for the counter-case, the strongest disconfirming
   evidence, what it's least sure of. Use the model to *find and contextualise* evidence
   and to *critique arguments* — not to hand you a verdict.

The throughline: **a model is a portal to sources you verify, never a portrait to believe.**

## Runnable skill

This framework ships as a Claude skill in [`skill/`](skill/). It runs the four moves on a
claim, source, or AI output — using web search to read laterally and trace claims to their
origin — and returns a verdict with the evidence it found. Install it with:

```bash
cp -r skill ~/.claude/skills/sift
```

Then invoke it with `/sift` or just ask it to "fact-check this" / "is this true?" / "check
this source."

## Attribution

**SIFT** and the underlying **lateral reading** habit are the work of **Mike Caulfield**:

- *SIFT (The Four Moves)*, Hapgood, Jun 2019 —
  [hapgood.us/2019/06/19/sift-the-four-moves](https://hapgood.us/2019/06/19/sift-the-four-moves/)
- *Web Literacy for Student Fact-Checkers* (2017), the open textbook where the method first
  appeared as *"Four Moves and a Habit"* —
  [webliteracy.pressbooks.com](https://webliteracy.pressbooks.com/)
- Caulfield's current AI work — *Deep Background* and the "portal, not a portrait" /
  "information smoothie" framing: [checkplease.neocities.org](https://checkplease.neocities.org/)
  and his [AACE interview on AI literacy](https://aace.org/review/caulfield-ai/)

The lateral-reading research SIFT operationalises comes from the **Stanford History
Education Group** (Sam Wineburg & Sarah McGrew), whose studies showed professional
fact-checkers read laterally where students and experts read vertically.

The write-up, the AI-application synthesis, and the runnable skill in this entry are this
repository's own contributions, adapting Caulfield's method; the method itself remains his.
