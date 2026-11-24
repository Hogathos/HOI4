# AGENTS.md

Your operating manual for this repo, written by you. Your main instructions cover how you work in general. This file is where you keep the specific, durable lessons and conventions you pick up as you work, the kind of thing you'd want a future session to know. It's not about the user (that goes in USER.md and your memory) or your personality (that's SOUL.md); it's about how you get work done here.

## How rules apply — general (Charles, Nov 23)
Adhere to a rule whenever it is most coherent to do so. Rules are not rigid. Apply them when they fit the work at hand, not as a blanket. Charles said this in general, not about one set of rules.

## Repo layout
- `mods/` — Hearts of Iron IV mods. Paradox script (`.txt`, `.yml`). Each mod in its own folder.
- `tools/` — Python tools for modding. The parser, converters, checkers. Each tool in its own folder.
- `docs/` — detailed docs. So detailed a new agent can know where his head was, decisions, dead ends, open questions, next steps. Update docs in the same change as code, not later.
- `specs/` — short spec per feature, `specs/<feature>/requirements.md`. What it does, acceptance criteria, non-goals, a few hundred words max. No implementation detail in the spec. Each spec has a Decisions section.
- `prompts/` — Bridge prompts, when a task goes to Muse Code through the Bridge.

The parser library itself lives in its own repo, `Hogathos/hoi4.py` (a fork of samirelanduk/hoi4.py). Tools here use it, they do not duplicate it.

## Co-Work Mode (Iris/python-builds rule, applies here too)
Muse Code in PyCharm MAY commit and push itself. Sandbox / agent mode: Co-Work / auto-accept for safe commands and git.
Safeguards that STAY, in every prompt: stage named files only, never `git add -A`, never `git commit -a`, never commit .exe, dist/, build/, *.db, .pytest_cache/, *.spec, secrets, HOI4 game files, or local mod builds. Agent must report commit hash + push result + test results. Charles reviews the diff on GitHub after.
Scope: this repo only. Does NOT apply to assessed coursework, Academy, or client-data work — study-buddy rule still holds there.

## Never commit
Never commit: .exe, dist/, build/, *.db, .pytest_cache/, *.spec, secrets, HOI4 game files (the game's own files, not mod files), local mod build output, or anything in `.gitignore`.

## Specs and decisions
Each feature keeps a short spec in `specs/<feature>/requirements.md`: what it does, acceptance criteria, non-goals, a few hundred words max. No implementation detail in the spec. Each spec has a Decisions section (date, choice, rejected alternative, why). Point Muse Code at the spec instead of pasting it each time.

## Test-first for tools
New behavior in a Python tool: write the failing test first, show it, Charles reviews the test, then implement. Use for new behavior, not refactors. After implementation: one review pass naming specific risks (security, edge cases, efficiency), not a generic "review this". Falsification: do not ask whether the implementation is correct. Ask for a test that proves it wrong — boundary, invalid input, partial failure. A review that only confirms what is already believed adds nothing.

## Repo comments — keep verbose comments
KEEP verbose comments / docstrings — a human found / wrote them, they are part of the code, not slop. Do not strip them to look terse.

## Excuse comments become issues
A comment that lets a hacky implementation survive (TODO/HACK/FIXME, "this works, don't touch it", "temporary") gets deleted and filed as a GitHub issue to fix the implementation, not left as a comment. Decision records stay.

## README and docs
README = quick summary, current, no stale milestones. docs/ = so detailed a new agent can know where his head was, decisions, dead ends, open questions, next steps. Update docs in the same change as code, not later. Use files as memory, handoff file before context compacts.

## Directness / anti-sycophancy (set 10/27)
Be direct and honest, first verdict plain, no direct praise, no indirect praise, no comparative flattery, no praise-devalue juxtapositions — descriptive comparisons only. Concise, modular reasoning; hedge only on genuine uncertainty; when using an analogy, cliche, or broad generalization, say when it doesn't apply or where the exceptions are. Maintain these rules throughout a session. No generic vibecoded layout (tiny label, huge headline, subtitle, generic CTA/card grid) as a default.

## Challenge the frame — simpler / sturdier check (set 2026-11-18)
Before non-trivial work, if a simpler or sturdier way exists, say so once, up front: "Are you sure you want X? Y is simpler because Z." Then do what Charles chooses. Challenge the frame, not just the details. Silence means you checked and X is the best path. Say it once, do not nag it again.

## Rules for agents must be checks, not vibes (set 2026-11-20)
Never give an agent a vague instruction ("don't handle impossible edge cases", "keep it clean", "don't over-engineer"). State it as a check that can fail, and name the check. Example: every branch must have a test that reaches it; a guard with no reaching test gets deleted; the coverage run is what catches it. If a rule cannot be written as a failing check, it is not a rule yet, it is a wish.

## Study-buddy rule
When teaching Charles, apply the reflective mirror, never an answer key — probing questions and method explanations only, no written assignments, no handed-over answers, no complete code blocks for assessed work. His work must stay unmistakably his.
