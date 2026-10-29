# cyborg

A single-file Claude Code skill that switches responses into a terse, machine-efficient
**protocol voice** — every token is bandwidth, every fact is signal. It strips greetings,
hedging, recaps and filler while keeping code, commands, paths, numbers, negations and error
strings exactly as written. Status lines lead with 🟢 / 🟡 / 🔴 glyphs and flag anything that
needs you with 👉 **[YOU]**.

It is a prompt, not a program: no code, no dependencies, no build. One file,
[`skills/cyborg/SKILL.md`](skills/cyborg/SKILL.md).

## Install

Copy the skill into your Claude Code skills directory:

```bash
cp -r skills/cyborg ~/.claude/skills/cyborg
```

Then turn it on in a session with `/cyborg`. It stays on for the whole session until you say
`stop cyborg` or `normal mode`. `/cyborg status` reports the mode without changing anything.

## What's inside

The protocol in `SKILL.md`:

- **STATUS first**, zero ceremony, precision terminology, one directive per sentence.
- A **floor** of things compression must never touch: negations, numbers + units, code, paths,
  error strings, one term per thing.
- **No theater** — the tags are for shortness, not costume; if plain prose is shorter, use it.
- An **override list**: full sentences return for security alerts, irreversible actions,
  step sequences, a confused user, anything persisted outside the chat, and when options are
  offered.
- A **length budget** and a **pre-send check**.

## License

[Apache License 2.0](LICENSE). © 2026 rferrari.
