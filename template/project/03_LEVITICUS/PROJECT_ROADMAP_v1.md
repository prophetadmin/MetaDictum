# PROJECT_ROADMAP_v1.md

This scaffold placeholder does not count as a generated roadmap artifact until
it is replaced with schema-conforming roadmap content.

This file is generated during project bootstrap.

Purpose
Define the deterministic execution plan for the project.

Generation
Created by running `/create_map_v2`, which applies:

`03_LEVITICUS/Core/PLANNER_TO_ROADMAP_TRANSFORMATION_PROMPT_v2.md`

to

`01_GENESIS/PROJECT_SEED.md`
`01_GENESIS/REQUIREMENTS_LEDGER.md`
`01_GENESIS/COMPONENT_REALIZATION_MAP.md`

Structure
The roadmap must conform to:

`03_LEVITICUS/Core/ROADMAP_SCHEMA_v2.md`

Lifecycle

`01_GENESIS/IDEA.md`
-> `/seed`
-> `01_GENESIS/PROJECT_SEED.md`
-> `/create_map_v2` preprocessing
-> `01_GENESIS/REQUIREMENTS_LEDGER.md` + `01_GENESIS/COMPONENT_REALIZATION_MAP.md`
-> `PROJECT_ROADMAP_v1.md`
-> `/status_sync` and runtime execution

Notes

* The roadmap is versioned when legitimate misses or new constraints are discovered.
* Roadmap revisions must create new versions (`PROJECT_ROADMAP_v2.md`, etc.).
* Roadmap generation must be best-effort comprehensive from seed-derived architecture and requirements-ledger decomposition.
* Every phase must include canonical receipt-aware completion criteria and a canonical receipt artifact under `03_LEVITICUS/Execution/`.
