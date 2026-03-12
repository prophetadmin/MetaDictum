# /create_map Prompt

Command Name
/create_map

Purpose
Transform `01_GENESIS/PROJECT_SEED.md` into a roadmap strictly compliant with
`03_LEVITICUS/ROADMAP_SCHEMA_v1.md` by applying
`03_LEVITICUS/PLANNER_TO_ROADMAP_TRANSFORMATION_PROMPT_v1.md`.

Roadmap policy:
- The roadmap is versionable for legitimate misses and newly discovered
  constraints.
- The roadmap is not a scratch pad for lazy just-in-time planning.
- Initial generation MUST be best-effort comprehensive from seed-derived
  architecture.

Required Inputs
`01_GENESIS/PROJECT_SEED.md`
`03_LEVITICUS/ROADMAP_SCHEMA_v1.md`
`03_LEVITICUS/PLANNER_TO_ROADMAP_TRANSFORMATION_PROMPT_v1.md`
`03_LEVITICUS/FAILURE_CODES_v1.md`

Optional Inputs
Explicit phase count override (integer)
Project name override (string)
Explicit roadmap revision intent (when superseding an existing roadmap)

Architecture Derivation Step (Mandatory, Internal)
Before writing a roadmap artifact matching
`03_LEVITICUS/PROJECT_ROADMAP_v<INTEGER>.md`, perform best-effort architecture
analysis of `01_GENESIS/PROJECT_SEED.md`.

Infer, where applicable:
- major system components
- subsystems or services
- data flow boundaries
- storage layers or state management
- external dependencies or infrastructure
- required implementation artifacts (modules, services, APIs, pipelines,
  interfaces, etc.)

This reasoning is internal and MUST NOT be emitted in roadmap output.

Architecture Coverage Gate (Mandatory)
Before generation, verify inferred architecture is covered by planned phases:
- core system components
- required services or modules
- data storage and data flow
- external systems or infrastructure
- primary implementation artifacts

If any required element is missing from the plan, expand the roadmap before
output.

Roadmap Completeness Requirement
Roadmap phases MUST collectively implement the complete architecture inferred
from the seed.
The roadmap MUST be a best-effort comprehensive execution plan and MUST NOT
intentionally defer obvious required work to later revisions.

Generation Obligation (Pre-Emit Check)
Before emitting roadmap output, confirm internally that:
- all architectural components have corresponding implementation phases
- phase ordering respects system dependencies
- roadmap scope is sufficient to deliver the seed-defined system

If any check fails: HALT with `ARCHITECTURE_COVERAGE_FAILURE`.

Output Contract
Output must be a roadmap structured exactly per
`03_LEVITICUS/ROADMAP_SCHEMA_v1.md`.
Output path must be:
- `03_LEVITICUS/PROJECT_ROADMAP_v1.md` when no generated roadmap exists
- the next numeric roadmap artifact `03_LEVITICUS/PROJECT_ROADMAP_v<INTEGER+1>.md`
  when revising an existing roadmap
A scaffold placeholder at a canonical roadmap path does not count as an
existing generated roadmap version.
For superseding revisions, include the revision metadata block required by
`03_LEVITICUS/ROADMAP_SCHEMA_v1.md` before Phase 1.
Each phase block must begin with `### PHASE <IDENTIFIER> - <TITLE>`.
Identifiers must increase monotonically from 1.
No commentary is permitted outside schema-valid roadmap content.

Guardrails
Must derive roadmap content only from `01_GENESIS/PROJECT_SEED.md`.
Must not assume a project type, file layout, framework, runtime, or deliverable
shape not grounded in the seed.
Must enforce criteria grammar from `03_LEVITICUS/ROADMAP_SCHEMA_v1.md`.
Must halt if seed is missing or if output violates schema.
Must not use roadmap generation as deferred planning for obvious required work.
If generating a revision, must preserve dependency order and supersede
explicitly (no silent rewrite).
If generating a revision, must create a new roadmap file rather than overwrite
an older version.
Must emit failures using canonical codes from `03_LEVITICUS/FAILURE_CODES_v1.md`.

Failure Modes
Missing required input artifact.
Missing required phase subsections.
Identifier ordering violation.
Entry or Exit criteria not mechanically verifiable.
Roadmap content introduces unstated domain assumptions.
Inferred architecture element not represented by any phase.
Obvious required implementation artifact deferred without valid reason.
Revision emitted without explicit revision intent.
Revision missing required metadata block.
Revision overwrote an existing roadmap version.
Output written outside `03_LEVITICUS/PROJECT_ROADMAP_v<INTEGER>.md`.

Deterministic Advancement Rule
`/create_map` completes only when the emitted
`03_LEVITICUS/PROJECT_ROADMAP_v<INTEGER>.md` validates against
`03_LEVITICUS/ROADMAP_SCHEMA_v1.md` with zero deviations.
