# MetaDictum Quick Start

This guide is the practical first-use path for starting a MetaDictum project.

## 1. Idea Formation

Before using the template, spend time exploring the project with a capable
model or collaborator.

Use that stage to clarify:

- the problem being solved
- who the project is for
- desired outcomes
- important constraints
- environment assumptions
- technical facts already known
- what the project will not attempt to do

The goal is to turn rough discussion into a usable project idea, not to begin
execution prematurely.

## 2. Author `01_GENESIS/IDEA.md`

Write the selected project idea into `01_GENESIS/IDEA.md`.

This is the primary ideation artifact used to begin bootstrap.

A stronger `IDEA.md` usually reduces roadmap revisions later.

## 3. Run `/seed`

Run `/seed` to transform `01_GENESIS/IDEA.md` into
`01_GENESIS/PROJECT_SEED.md`.

This step converts the idea artifact into a more structured seed suitable for
roadmap generation.

## 4. Run `/create_map_v2`

Run `/create_map_v2` to transform `01_GENESIS/PROJECT_SEED.md` into the initial
roadmap artifact at `03_LEVITICUS/PROJECT_ROADMAP_v1.md`.

## 5. Run `/status_sync`

Run `/status_sync` to initialize and normalize
`03_LEVITICUS/STATE_SUMMARY.md`.

This establishes the canonical execution state before work begins.

## 6. Continue with `/resume_phase`

Use `/resume_phase` as the practical default for deterministic execution.

Use `/resume` instead when you want to advance the project one deterministic
objective at a time.

## Notes

- MetaDictum can run with incomplete inputs, but stronger inputs usually
  produce better roadmaps.
- If important project facts are missing at the start, expect more roadmap
  revisions and clarification work later.
- Optional commands such as `/summarize_session` and `/extract_canon` are not
  required for normal execution.
