# REQUIREMENTS_LEDGER.md

This scaffold placeholder does not count as a generated requirements ledger artifact until it
is replaced with schema-conforming requirements content.

This file is created during the bootstrap phase of a MetaDictum-governed project.

Purpose
Normalize the project seed into a binding requirements and component inventory for roadmap generation.

Generation
Created during `/create_map_v2` bootstrap preprocessing by applying:

`03_LEVITICUS/Core/REQUIREMENTS_DERIVATION_PROMPT_v1.md`

to

`01_GENESIS/PROJECT_SEED.md`

Structure
This file must conform to:

`03_LEVITICUS/Core/REQUIREMENTS_LEDGER_SCHEMA_v1.md`

Lifecycle

`01_GENESIS/IDEA.md`
-> `/seed`
-> `PROJECT_SEED.md`
-> requirements derivation
-> `REQUIREMENTS_LEDGER.md`
-> roadmap generation (`/create_map_v2`)

Notes

* This file does not count as generated until it is replaced with schema-valid requirements content.
* The requirements ledger is a binding planning input for roadmap generation.
* The roadmap must not be generated until this file exists and conforms to schema.
* `/create_map_v2` must treat this ledger inventory as binding for coverage and phase planning.
