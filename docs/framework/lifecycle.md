# MetaDictum Lifecycle

MetaDictum has two operational stages:

1. Bootstrap Mode, where planning artifacts are generated.
2. Execution Mode, where roadmap phases are executed and state is normalized.

A workspace moves into Execution Mode once a generated roadmap artifact exists
at `03_LEVITICUS/PROJECT_ROADMAP_v<INTEGER>.md`.

## Bootstrap Mode

Bootstrap starts from:

`01_GENESIS/IDEA.md`

The canonical bootstrap chain is:

1. `/seed`
2. `/derive_requirements`
3. `/realize_components`
4. `/create_map_v2`
5. `/validate_map_v2`

That chain produces the hardened planning bridge:

- `01_GENESIS/PROJECT_SEED.md`
- `01_GENESIS/REQUIREMENTS_LEDGER.md`
- `01_GENESIS/COMPONENT_REALIZATION_MAP.md`
- `03_LEVITICUS/PROJECT_ROADMAP_v1.md`

Each stage narrows ambiguity before execution:

- `PROJECT_SEED.md` captures the project intent derived from `IDEA.md`
- `REQUIREMENTS_LEDGER.md` normalizes mandatory requirements from the seed
- `COMPONENT_REALIZATION_MAP.md` assigns concrete `02_EXODUS/` artifact
  ownership to those requirements
- `PROJECT_ROADMAP_v1.md` turns the seed, requirements ledger, and realization
  map into executable phases
- `/validate_map_v2` confirms the roadmap preserves schema, requirements
  coverage, realization coverage, and seed coverage before runtime begins

For fresh or reset workspaces, `/bootstrap` is the canonical orchestrator for
this chain.

## Execution Mode

Once a generated roadmap exists, runtime starts with:

`/status_sync`

This normalizes canonical execution state into:

`03_LEVITICUS/STATE_SUMMARY.md`

From there, the normal runtime pattern is:

1. `/status_sync`
2. `/resume_phase`
3. repeat in the next session or for the next active phase

`/resume_phase` handles repeated `/resume` execution for the current Active
Phase. When the next unmet criterion is the canonical phase receipt criterion,
it must execute `/record_phase_completion` before continuing. After the phase
loop completes, it runs `/status_sync` exactly once.

Use `/resume` directly only when you intentionally want single-step
deterministic advancement instead of phase-level continuation.

Use `/record_phase_completion` directly only when all non-receipt Exit
Criteria for the active phase are already directly proven and the next unmet
criterion is the canonical phase receipt.

Canonical phase receipts are written under:

`03_LEVITICUS/Execution/`

## Layer Roles

- `01_GENESIS/` holds the original idea plus bootstrap planning artifacts
- `02_EXODUS/` holds implementation artifacts owned and produced by roadmap
  execution
- `03_LEVITICUS/` holds governance, roadmap, prompts, schemas, normalized
  runtime state, and canonical phase receipts
- `05_NUMBERS/` can hold optional session summaries or operational records
- `04_DEUTERONOMY/` can hold optional distilled canonical outputs after the
  project is stable or complete

## Optional Continuity And Distillation

Normal execution does not require session logging or canon extraction.

`/summarize_session` is optional and can preserve concise session memory in
`05_NUMBERS/`.

`/extract_canon` is optional and can promote stable distilled outputs into
`04_DEUTERONOMY/` after the project is complete or otherwise mature.
