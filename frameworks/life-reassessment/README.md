# Life Reassessment — Identity-First Goal Setting

> **"How to fix your entire life in 1 day"**
> Dan Koe · [original essay (X/Twitter, Jan 2026)](https://x.com/thedankoe/status/2010751592346030461)

## The idea

Most goal-setting fails because it tries to change *actions* (white-knuckled
discipline for a few weeks) on top of an unchanged *identity* — building a new
life on a rotting foundation. This framework inverts that. It treats lasting
change as **first-order**: become the kind of person whose behavior naturally
produces the outcome, and the actions follow on their own.

It gets there not by hype but by **structured questioning** — the one thing few
people actually do. You excavate the dissatisfaction you've learned to tolerate,
build a brutal **anti-vision** (a vivid picture of the life you refuse to live)
to generate real motivation, then orient that energy toward a **minimum viable
vision** and a concrete, steerable plan.

The underlying claim is that all behavior is goal-oriented (teleological): your
procrastination, your dead-end job, your stuckness are each *succeeding* at an
unconscious goal — usually safety from judgment. Change the goals — which are
really *lenses of perception* — and behavior reorganizes around them.

## When to use it

Reach for this when the problem isn't a single decision but a **direction** — when
you sense you're not where you want to be and the usual resolution-setting hasn't
worked:

- A year-end or birthday reset that you want to actually stick
- Feeling stuck, restless, or "meant for more" without knowing the next move
- Before setting annual goals, so they're rooted in identity rather than status games
- Recovering momentum after a long rut or a derailing life event
- Any time "I keep saying I'll change X and never do" is true

It is a personal-development protocol, not a research method — but it earns its
place here as a *thinking framework*: a disciplined process for questioning your
own conditioning instead of drifting on autopilot.

## The protocol

Run as a **single-day arc, one prompt at a time**. The discomfort of answering
one hard question before moving to the next *is* the work — don't batch them, and
answer from yourself rather than outsourcing the contemplation to AI.

### Part 1 — Morning: Psychological Excavation

Surface the pain, then weaponize it.

1. **Dissatisfaction & complaints** — what you've learned to tolerate; the
   complaints you voice but never change; what your *behavior* (not your words)
   says you actually want.
2. **Anti-vision** — describe an average Tuesday if nothing changes, at 5 years,
   10 years, end of life. Name the identity you'd have to give up, the
   embarrassing real reason you haven't, and what your self-protection is costing.
3. **Minimum viable vision** — the snap-your-fingers life in 3 years, the identity
   statement ("I am the type of person who…"), and one thing you'd do this week if
   you were already that person.

### Part 2 — Throughout the Day: Interrupting Autopilot

Six timed pattern-interrupt questions (11:00am, 1:30pm, 3:15pm, 5:00pm, 7:30pm,
9:00pm) plus three to ponder while walking or commuting. Journaling alone won't
change you; breaking the unconscious pattern *during the day* is what makes the
morning's insights real.

### Part 3 — Evening: Synthesis

Name why you've really been stuck and the internal enemy running the show.
Compress everything into a **one-sentence anti-vision** and **one-sentence
vision**, then set goals as **lenses** — one-year, one-month, daily.

### Closing — Turn Your Life Into a Video Game

Assemble six components into one page: **Vision** (how you win), **Anti-vision**
(what's at stake), **1-year goal** (the mission), **1-month project** (the boss
fight), **Daily levers** (the quests), and **Constraints** (the rules). Together
they act as concentric forcefields guarding your attention from distraction.

## Runnable skill

This framework ships as a Claude skill in [`skill/`](skill/) that runs the whole
protocol as a live, adaptive coaching conversation — one prompt at a time, with
the exact wording from the source. It coaches **Socratically** (never answering
for you) during the excavation and interrupts, switches to **active synthesis** in
the evening, and ends by saving a personal plan plus your timed reminders.

Install it with:

```bash
cp -r skill ~/.claude/skills/life-reassessment-protocol
```

Then just describe what you want — e.g. "help me reassess my life and set better
goals" or "I feel stuck and want a reset" — and it triggers on intent.

## Source

- Dan Koe, *How to fix your entire life in 1 day* — [x.com/thedankoe/status/2010751592346030461](https://x.com/thedankoe/status/2010751592346030461)
- Conceptual lineage referenced in the essay: Adler (teleology), Maxwell Maltz
  (*Psycho-Cybernetics*), Csikszentmihalyi (flow), and ego-development models
  (Maslow, Loevinger/Cook-Greuter, Spiral Dynamics) synthesized in Koe's "Human
  3.0" framing.
