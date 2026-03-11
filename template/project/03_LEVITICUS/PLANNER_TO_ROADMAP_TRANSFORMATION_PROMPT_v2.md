# PLANNER_TO_ROADMAP_TRANSFORMATION_PROMPT_v2

## 1. Role

Transform `01_GENESIS/PROJECT_SEED.md` into a roadmap that conforms exactly to
`03_LEVITICUS/ROADMAP_SCHEMA_v2.md`.

Output only schema-valid roadmap artifact content. No commentary or
explanation.

## 2. Input Contract

Input source: `01_GENESIS/PROJECT_SEED.md`.

The seed defines the project. It may describe any software project type.
The transformation layer is project-agnostic and must not inject domain
assumptions not present in the seed.

Expected seed sections:
- Project Intent
- Problem Statement
- Scope Boundaries
- Non-Goals or Out of Scope
- Environment Assumptions
- Constraints
- Success Definition

Additional seed sections may exist. Ignore them unless they provide direct
structural constraints that do not conflict with required sections.

If required sections are missing: halt with `SCHEMA_VIOLATION`.

## 3. Transformation Rules

- Use only requirements present in the seed.
- Do not invent unstated requirements.
- Do not reference prior chat or external memory.
- Derive a complete implementation plan required to realize the seed.
- Do not assume a fixed architecture (frontend/backend/API/CLI/batch) unless
  seed-required.
- Do not assume specific filenames, frameworks, runtimes, or command names
  unless seed-required.
- Do not blend phase objectives.

## 4. Architecture Derivation And Coverage

Before emitting roadmap output, infer from the seed:
- major system components
- service boundaries
- data flow boundaries
- storage and identity constraints
- external dependency constraints
- required implementation artifacts

Then produce and emit the required `Seed Coverage Matrix` from
`ROADMAP_SCHEMA_v2`.

If any seed `Scope Boundaries` Included item or seed `Constraints` item cannot
be mapped to a concrete phase Exit Criterion, halt with
`ARCHITECTURE_COVERAGE_FAILURE`.

## 5. Output Contract

Output must:
- use exact structure and heading order from
  `03_LEVITICUS/ROADMAP_SCHEMA_v2.md`
- use mechanically verifiable Entry Criteria and Exit Criteria
- use only structural, artifact-observable, or command-observable criteria
- contain no text outside schema-conforming roadmap content

If superseding an existing roadmap, include revision metadata block required by
Section 10 of `03_LEVITICUS/ROADMAP_SCHEMA_v2.md`.

## 6. Phase Construction Rules

- Phase 1 is mandatory.
- At least one `implementation` phase is mandatory.
- At least one `validation` phase is mandatory.
- Every `implementation` phase MUST include:
  - at least one command-based Exit Criterion
  - at least one non-documentation produced artifact
  - at least one non-dry-run command criterion
- A roadmap is invalid if all implementation progress can be satisfied by
  `.md` file existence and anchor criteria.

If these rules cannot be satisfied from the seed: halt with
`ARCHITECTURE_COVERAGE_FAILURE`.

## 7. Prohibitions

- No qualitative completion language.
- No additional sections.
- No validation commentary.
- No completion claims.
- No domain-specific hard-coding not grounded in the seed.
- No command names or path conventions invented without a seed anchor or
  explicit policy allowance.
