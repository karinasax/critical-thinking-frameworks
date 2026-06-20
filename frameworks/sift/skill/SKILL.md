---
name: sift
description: >-
  Fact-check a claim, source, or AI output using Mike Caulfield's SIFT method — Stop,
  Investigate the source, Find better coverage, Trace claims to the original context —
  with lateral reading via web search. Use this whenever the user wants to know whether
  something is true or trustworthy before believing, sharing, or acting on it: a claim,
  statistic, quote, "study says…," a news article or link, a screenshot or image, a
  social post, or a citation/source an AI produced. Trigger it on "is this true,"
  "fact-check this," "can I trust this source," "did this really happen," "check this
  claim," "verify this," "SIFT this," or any moment where a confident-sounding statement
  needs verification before it's relied on. Especially reach for it when checking an
  LLM's own claims and citations — confident references that turn out to be fabricated or
  misattributed are the failure mode this catches. For deep multi-perspective research
  rather than fast verification, use the storm skill instead.
---

# SIFT: Fact-Checking in Four Moves

## What this does and why it works

A confident, well-written claim is the easiest thing to believe and the easiest thing to
fake — and an LLM produces them by default. SIFT (Mike Caulfield) is the counter-habit:
instead of scrutinising a source on its own terms, you leave it and check what the rest of
the web says, find the best available coverage of the claim, and trace it back to where it
actually came from. The habit underneath all four moves is **lateral reading** — judging a
source by its reputation among people who'd know, not by what it says about itself.

For AI specifically: model output is an **"information smoothie"** — fluent and confident
with the provenance blended out. Treat it as **a portal to sources you verify, not a
portrait to believe.** The *Trace* move is what catches the AI-specific failure: confident
claims backed by citations that don't exist, don't say what's claimed, or are misattributed.

This skill runs the four moves with **real web search** so verification is grounded, not
recalled — then returns a verdict with the evidence behind it.

## Before you start: identify what's being checked and why

1. **The claim or source.** Pin down the *specific, checkable* assertion. "This article is
   biased" isn't checkable; "this article says vaccine X caused N deaths" is. If the user
   pasted a long thing, extract the one or two load-bearing claims worth verifying and say
   which you're checking.
2. **The stakes.** How much effort a claim deserves depends on what the user will do with
   it. A passing curiosity gets a 30-second pass; something they're about to publish,
   forward widely, or make a decision on gets all four moves, hard. Calibrate, and say so.

If the source is an AI's own output (a claim or citation it generated), say so explicitly —
that flags *Trace* as the priority move.

## The mindset

- **Lateral reading is the whole game.** Don't evaluate a source by reading it more
  closely. Open other sources and ask what *they* say about it. Most of your moves should
  leave the original behind.
- **You don't always need the source — sometimes you need the claim.** If the question is
  "is this true," go straight to *Find better coverage*; the original's credibility may be
  irrelevant.
- **Reputation and consensus, not a single hit.** You can always find *one* page that
  agrees. Look for the weight of credible reporting.
- **State your confidence honestly.** "I couldn't verify this" is a real, useful result.
  Don't manufacture certainty.

## The workflow

Run the moves that fit — they're not a rigid sequence — but **always Stop first**, and use
web search for the lateral moves rather than relying on what you already know. Tell the user
which moves you're running and why.

Announce briefly: "Running SIFT — I'll check the source, find better coverage, and trace
the claim to its origin."

---

### S — Stop

Set up the check before diving in:

- State the **specific claim(s)** you're verifying, extracted from what the user gave you.
- Flag the **emotional charge** — if the content is engineered to provoke outrage or
  delight, name that; manipulation rides on emotion.
- Note the **stakes** and how much scrutiny that warrants.
- If the source is **AI-generated**, say so — *Trace* becomes the priority.

---

### I — Investigate the source

Read **laterally** about whoever is making the claim — *do not* rely on their own
about-page or self-description. Use web search:

- Who is this author / publication / account / site? What's their expertise and track
  record on *this* topic?
- What's their agenda, funding, or known bias? What do independent sources say about them?
- Is the source even real and current — or impersonating, satirical, or defunct?

Report what you found and how it reframes the claim. If the source turns out not to matter
(the claim is checkable independently), say so and move to *Find*.

---

### F — Find better coverage

Leave the source and search for the **best available coverage of the claim itself**:

- Do credible outlets, domain experts, or fact-checkers corroborate, contradict, or
  contextualise it?
- Is there a **consensus of reporting**, or only a single confirming source?
- Has it already been fact-checked or debunked?

Report the weight of evidence, not a cherry-picked hit. If reputable sources conflict, say
so plainly rather than picking a side.

---

### T — Trace claims, quotes, and media to the original context

Follow the claim back to its **origin** and check it against the secondhand version:

- Find the original study, full quote, primary document, or uncropped image.
- Does the original actually say what's claimed, or has it been cherry-picked, stripped of
  context, or distorted?
- **For AI output:** open every citation the model gave. Does the source exist? Does it say
  what was claimed? Is it correctly attributed? A plausible-looking but fabricated or
  misattributed reference is the most common AI failure — flag it explicitly.

If you can't reach the original, say that — an untraceable claim is itself a finding.

---

## Output: the verdict

Close with a short, honest verdict:

- **What the claim is** and **what you found** — corroborated, contradicted, missing
  context, unverifiable, or false.
- **A confidence level** (e.g. high / moderate / low) with the reason for it.
- **The strongest evidence** for and against, with the sources you actually used (as links).
- **What's still open** — anything you couldn't verify and what would settle it.

End with a one-line bottom line: can the user trust this, and to what degree.

## Working with AI output specifically

When the thing being checked is a language model's claim, layer in Caulfield's three AI
moves: **get it in** (pull the real source into context rather than trusting recall),
**track it down** (make the claim produce a source, then *Trace* it), and **follow up**
(ask for the counter-case and the model's least-confident points). The throughline: a
model is a portal to sources you verify, never a portrait to believe.

## When the user just wants a fast take

For a low-stakes, passing question, run a quick *Stop + Find better coverage* pass and give
a one-paragraph verdict with confidence. Save the full four-move treatment for claims the
user is about to rely on, publish, or share widely — and say which level you're giving.

## Note on grounding

This skill is only as good as its lateral reading — **use web search for the Investigate,
Find, and Trace moves.** Verifying a claim from your own training data defeats the purpose
and risks confirming a falsehood. If web search is unavailable, say so and downgrade your
confidence accordingly rather than presenting a recalled answer as verified.

## Attribution

SIFT and the lateral-reading habit are the work of **Mike Caulfield** — *SIFT (The Four
Moves)*, Hapgood, 2019 (hapgood.us/2019/06/19/sift-the-four-moves/), first published as
*"Four Moves and a Habit"* in *Web Literacy for Student Fact-Checkers* (2017). The
"information smoothie" and "portal, not a portrait" framings and the three AI moves are
Caulfield's (checkplease.neocities.org). The lateral-reading research it operationalises
is from the Stanford History Education Group (Wineburg & McGrew). This skill is this
repository's own adaptation of the method into a runnable, web-grounded workflow.
