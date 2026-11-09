# cyborg

A single-file Claude Code skill that switches responses into a terse, machine-efficient
**protocol voice** — every token is bandwidth, every fact is signal. It strips greetings,
hedging, recaps and filler while keeping code, commands, paths, numbers, negations and error
strings exactly as written. Status replies read as **system log lines** (`SYSTEM>`, `ACTION>`,
`SESSION>`), with colored glyphs only where something needs attention and one trailing
**👉 YOU>** line for what only the human can do.

It is a prompt, not a program: no code, no dependencies, no build. One file,
[`skills/cyborg/SKILL.md`](skills/cyborg/SKILL.md).

## Install

Copy the skill into your Claude Code skills directory:

```bash
cp -r skills/cyborg ~/.claude/skills/cyborg
```

Then turn it on in a session with `/cyborg`. It stays on for the whole session until you say
`stop cyborg` or `normal mode`. `/cyborg status` reports the mode without changing anything.

## Companion skill: brainstorm

[`skills/brainstorm/SKILL.md`](skills/brainstorm/SKILL.md) is a second, independent skill for the same way of working.
When you float an idea mid-task ("maybe...", "what if...", "idk"), it is written to the project's backlog as a
numbered entry with open questions, **not built**; ideas get reviewed later and only then planned. It does not
depend on `cyborg`, and `cyborg` does not depend on it.

```bash
cp -r skills/brainstorm ~/.claude/skills/brainstorm
```

## What a reply looks like

```text
SYSTEM> keepkey-mobile | PR#8 OPEN | merge NOT allowed
ACTION> fresh review run, 1 finding, fix pushed
BLOCKED review limit, resets ~23:07
👉 YOU> say `check handoff`
```

- **Labels in full:** `SYSTEM>` state, `ACTION>` something done and its result, `SESSION>` an agent,
  session or inbox. No SYS/SES/ACT abbreviations.
- **Format:** `key=value` and `|` separators, one line per item. NOT / NO / never are kept verbatim.
- **Glyphs, sparingly:** 🔴 blocked or failed, 🟡 waiting on someone, 🟢 only a finished milestone.
  Plain lines carry no glyph.
- **Color:** chat reaches the terminal as markdown, so real color is not possible. Don't wrap
  status in a fenced code block (it renders as one solid color). Write normal lines as plain
  text and put only the `ACTION>` label and attention keywords in inline code, which many
  terminals color. This README shows it in a block only so you can see the layout.
- **Length:** at most 6 lines by default, result first, details in a file with its path.
- **Full sentences instead** for security alerts, irreversible actions and anything a fragment
  could scramble.

## What's inside

The protocol in `SKILL.md`:

- **Answer first**, zero ceremony, precision terminology, one directive per sentence.
- A **floor** of things compression must never touch: negations, numbers + units, code, paths,
  error strings, one term per thing.
- **No theater** — the tags are for shortness, not costume; if plain prose is shorter, use it.
- An **override list**: full sentences return for security alerts, irreversible actions,
  step sequences, a confused user, anything persisted outside the chat, and when options are
  offered.
- **Display rules** (labels, glyphs, color, length) and a **pre-send check**.

## License

[Apache License 2.0](LICENSE). © 2026 rferrari.
