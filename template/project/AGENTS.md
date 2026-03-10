# AGENTS.md

## Purpose
This file defines binding runtime behavior for agents in this workspace.

Goal: keep execution deterministic and lightweight while preserving bootstrap artifacts for future reuse.

## Scope
Applies to this template project only.

## Authority Order
1. Filesystem state
2. `03_LEVITICUS/Contracts/project_charter.md`
3. Canonical project artifacts (latest `03_LEVITICUS/PROJECT_ROADMAP_v<INTEGER>.md`, `03_LEVITICUS/STATE_SUMMARY.md`)
4. Chat output

Chat is never authoritative over repository state.

## Mode Switch (Automatic)
Scaffold placeholders may exist at canonical generated-output paths in a fresh
clone. Scaffold placeholders do not count as generated artifacts.

Bootstrap is complete when any generated roadmap artifact matching
`03_LEVITICUS/PROJECT_ROADMAP_v<INTEGER>.md` exists.

A roadmap artifact counts as generated only when it contains at least one phase
block heading matching:
`### PHASE <IDENTIFIER> - <TITLE>`

- If roadmap exists: Execution Mode
- If roadmap does not exist: Bootstrap Mode

No manual flags are required.

## Execution Mode (Default)
### Always Read
- latest `03_LEVITICUS/PROJECT_ROADMAP_v<INTEGER>.md`
- `03_LEVITICUS/STATE_SUMMARY.md`
- `03_LEVITICUS/Contracts/project_charter.md`

### Runtime Active
- `03_LEVITICUS/STATE_SUMMARY_SCHEMA_v1.md`
- `03_LEVITICUS/RESUME_PROTOCOL_v1.md`
- `03_LEVITICUS/FAILURE_CODES_v1.md`
- `03_LEVITICUS/Prompts/resume.md`
- `03_LEVITICUS/Prompts/resume_phase.md`
- `03_LEVITICUS/Prompts/status_sync.md`
- `03_LEVITICUS/Prompts/validate_phase.md`

### Conditional (Read Only When Needed)
- `03_LEVITICUS/ROADMAP_SCHEMA_v1.md`
  - Required for create/restructure/repair/validate operations on roadmap structure.
  - Not required for normal task execution or routine state updates.
- `03_LEVITICUS/SLASH_COMMAND_SPECS_v1.md`
  - Read only when command contract behavior is being changed or validated.
- `03_LEVITICUS/DRIFT_FAILURE_RULES_v1.md`
  - Read when drift is suspected, during audits, or while enforcing recovery behavior.

### Bootstrap-Only (Ignore During Execution Unless Explicitly Requested)
- `01_GENESIS/*IDEA*.md` (original ideation source files)
- `03_LEVITICUS/GENESIS_SEED_PROMPT_v1.md`
- `03_LEVITICUS/Prompts/seed.md`
- `03_LEVITICUS/PLANNER_TO_ROADMAP_TRANSFORMATION_PROMPT_v1.md`
- `03_LEVITICUS/Prompts/create_map.md`

## Bootstrap Mode
When roadmap does not exist, read and use:
- `01_GENESIS/*IDEA*.md` (if present)
- `01_GENESIS/PROJECT_SEED.md`
  - If present only as a scaffold placeholder, overwrite it with generated seed
    content before `/create_map`.
- `03_LEVITICUS/GENESIS_SEED_PROMPT_v1.md`
- `03_LEVITICUS/Prompts/seed.md`
- `03_LEVITICUS/PLANNER_TO_ROADMAP_TRANSFORMATION_PROMPT_v1.md`
- `03_LEVITICUS/Prompts/create_map.md`
- `03_LEVITICUS/ROADMAP_SCHEMA_v1.md`

Output of bootstrap phase:
- `03_LEVITICUS/PROJECT_ROADMAP_v1.md` on initial generation
- `03_LEVITICUS/PROJECT_ROADMAP_v<INTEGER+1>.md` on explicit revision

After roadmap creation, return to Execution Mode automatically.

## Roadmap Change Policy
Roadmap updates are allowed only with explicit revision intent.

Valid reasons:
- Missing requirement from seed discovered
- Dependency or constraint changes ordering/scope
- Scope correction required for feasibility
- New mandatory work introduced

Rules:
- No silent structural edits
- Record revision reason in the superseding roadmap metadata block
- Record execution impact in `03_LEVITICUS/STATE_SUMMARY.md` only when the
  revision changes active execution risks or deferrals
- Preserve prior intent when superseding sections

## Prohibitions
- Do not treat chat memory as canonical state.
- Do not auto-promote bootstrap artifacts into runtime context.
- Do not rewrite evidence/log intent without explicit instruction.

## Session Start Procedure
1. Detect mode by generated roadmap existence, not raw file presence.
2. Load only files allowed by that mode.
3. In Execution Mode, run `/status_sync` first.
4. Execute work from roadmap phases via `/resume`.
5. Update state summary with progress and decisions.
