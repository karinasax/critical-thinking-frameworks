# State & Resume (Day-Spread Mode)

In day-spread mode the protocol unfolds across a real day, so the user will leave
and come back. You need to (a) not lose their answers and (b) know exactly where
to pick up. The plan document itself is your state.

## Use the plan document as the source of truth

When the user picks day-spread mode, create the plan file immediately (from
`assets/plan-template.md`) and write each answer into it *as they go*, not just at
the end. This means:

- If the conversation ends or context is lost, the file holds everything done so
  far.
- Resuming = reading the file, seeing which sections are still empty, and
  continuing from the first unfilled section.

Add a small status line at the top of the file so resume is unambiguous:

```
<!-- PROTOCOL STATE: format=day-spread | last-completed=part1-anti-vision | next=part1-vision -->
```

Update that comment each time you finish a chunk. On resume, read it first.

## The day-spread flow

1. **Morning (now):** Run all of Part 1 (questions 1–14). Write answers into the
   plan file. Then generate the Part 2 reminders and (if a Reminders/Calendar
   tool is available and the user agrees) create them for today. Tell the user:
   "I'll be here when your interrupt questions start firing — just come back and
   tell me what came up, or save them for tonight."
2. **Daytime:** As the user returns reporting reflections from the timed
   questions, append them under the Part 2 section. Keep it light — these are
   field notes, not a second interview. The user may also just live the day and
   bring everything to the evening; that's fine.
3. **Evening:** Run Part 3 (questions 15–21) in active-synthesis mode, then
   assemble the six-component video-game plan. Finalize the document.

## Resuming a session

If the user comes back in a *new conversation* and the skill re-triggers:

- Look for an existing `~/life-reassessment-*.md` (most recent) or ask where they
  saved it.
- Read the PROTOCOL STATE comment and the filled sections.
- Briefly orient them ("Looks like you finished the morning excavation and your
  anti-vision — ready to move into tonight's synthesis?") and continue from
  `next`.

## If the user loses momentum

It's common to do the morning and not return. That's okay and worth normalizing.
On a later return, offer to either resume where they left off or re-read their own
anti-vision/vision aloud to re-anchor before continuing. Don't make them feel
they failed — Koe's own framing is that you quit far more goals than you keep.
