# MetaDictum Lifecycle

MetaDictum projects follow a simple progression:

1. Form and record the project idea in `01_GENESIS/IDEA.md`.
2. Generate `PROJECT_SEED.md` with `/seed`.
3. Generate a roadmap with `/create_map_v2`.
4. Normalize execution state in `03_LEVITICUS/STATE_SUMMARY.md`.
5. Execute deterministic objectives in `02_EXODUS/`.
6. Optionally summarize meaningful sessions into `05_NUMBERS/`.
7. Optionally extract distilled canon into `04_DEUTERONOMY/` after the project
   is complete or otherwise stable.

Bootstrap creates the initial roadmap. Runtime work then alternates between
state normalization, deterministic execution, and validation until phase exit
criteria are met.

## Layer Roles

- `01_GENESIS/` captures the initial idea artifact and seed inputs.
- `03_LEVITICUS/` defines governance and the execution plan.
- `02_EXODUS/` holds the implementation work that fulfills roadmap criteria.
- `05_NUMBERS/` can preserve high-signal session history when the user wants
  durable logs.
- `04_DEUTERONOMY/` can hold post-project or post-stabilization distilled canon.

## Optional Continuity and Distillation

MetaDictum does not require session logging or canon extraction for normal
operation.

`/summarize_session` is optional and exists for users who want concise session
memory in `05_NUMBERS/`.

`/extract_canon` is optional and exists for users who want distilled canonical
outputs in `04_DEUTERONOMY/`. It may be run after completion, including well
after day-to-day execution has ended.
