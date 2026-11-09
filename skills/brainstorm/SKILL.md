---
name: brainstorm
description: The user is thinking out loud: an idea, not a task. Use when a message floats an idea (often hedged: "idk", "maybe", "could be", "what if", "I imagine", "future") or the user types /brainstorm. Write it to the project's backlog; do not code it.
---

# brainstorm

The user thinks out loud while you build. An idea they float is **not a request to build it**. The flow is:

1. **Idea** (this skill): write it down in the backlog.
2. **Review**: later, together, read the backlog and decide what holds up.
3. **Plan**: a reviewed idea gets a plan with steps; only then is it built.

## Signals

- Hedged words: "idk", "i don't know", "maybe", "could be", "what if", "i imagine", "future".
- An idea dropped in the middle of other work, unrelated to the current step.
- `/brainstorm <idea>`.

If unsure whether a message is an idea or a go, it is an idea. "go", "do it", "build it", "start now",
"let's do it" are the go signals.

## What to do

1. **Don't write code, and don't read code in order to start building it.** Reading one file to name the right
   place in the note is fine; designing or implementing is not.
2. **Find the backlog.** The project's plan file and its backlog section. Look for `docs/*PLAN*.md`,
   `ROADMAP.md`, `BACKLOG.md`, or a section titled "Backlog" / "Ideas". If there is none, ask once where ideas
   should go, then use that place from then on.
3. **Add one numbered entry** at the end of the backlog list:
   - a bold short name, then `(who, YYYY-MM-DD)`;
   - the idea in the user's terms, in full sentences (keep their words, quoted, where they carry the meaning);
   - where it would touch, if obvious (one file or area, no design);
   - how it serves the project's stated direction, if the plan states one;
   - **Open:** the questions a review must answer.
   If the idea extends an existing entry, add to that entry instead of making a new one.
4. **Check facts you state.** If the note says what a tool, API or platform can do, either verify it or mark it
   "not verified". Correct a misremembered detail in the note instead of copying it (say so to the user).
5. **Project board, if the project has one.** If the project keeps a board (a file, or a tracker the user
   told you to use), add a card with the entry's number, short name, one line and its column. Do not create
   cards in an external tracker without the user's yes.
6. **Commit it locally** (docs only), following the repo's commit rules. Never push without being asked.
7. **Reply in two or three lines**: which entry number, the open questions, and that it waits for review. Then go
   back to the work that was in progress.

## Review (when the user asks to review the backlog)

Go through the entries in order. For each: what it would take, what it depends on, and a recommendation (plan it
now, keep, merge with another, drop). The entries the user picks get a plan; the rest stay.
