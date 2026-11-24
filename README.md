# HOI4

Hearts of Iron IV mods, tools, and parser — game modding.

## What is in here

- `mods/` — Hearts of Iron IV mods. Paradox script (`.txt`, `.yml`). Each mod in its own folder.
- `tools/` — Python tools for modding. The parser, converters, checkers. Each tool in its own folder.
- `docs/` — detailed docs. Decisions, dead ends, open questions, next steps.
- `specs/` — short spec per feature, `specs/<feature>/requirements.md`.
- `prompts/` — Bridge prompts, when a task goes to Muse Code through the Bridge.

## The parser

The parser library lives in its own repo, `Hogathos/hoi4.py` (a fork of samirelanduk/hoi4.py). It parses HOI4 save files, binary or plain text, and converts them to JSON. Tools here use it, they do not duplicate it.

## Rules

Read `AGENTS.md` before working in this repo. It holds the operating manual: Co-Work safeguards, what never gets committed, spec and test-first rules, and the directness rule.
