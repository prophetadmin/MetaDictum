# STATE_SUMMARY.md

This scaffold placeholder does not count as a generated continuity block until
it is replaced with schema-conforming state content.

This file records the current execution state of the project.

Purpose
Allow deterministic project continuation across sessions or agents.

Schema
This file must conform to:

`03_LEVITICUS/Core/STATE_SUMMARY_SCHEMA_v1.md`

Lifecycle

`/create_map_v2`
-> `PROJECT_ROADMAP_v<INTEGER>.md`
-> `/status_sync`
-> `STATE_SUMMARY.md`
-> `/resume_phase` (or `/resume`)
-> `/record_phase_completion`
-> `/status_sync`

Notes

* The state summary is initialized and normalized by `/status_sync`.
* The active phase is receipt-aware: a phase is not complete until required canonical receipt criteria are satisfied.
* This file determines the current project position.
* Agents must consult this file before executing work.

If this file is empty, execution has not yet begun.
