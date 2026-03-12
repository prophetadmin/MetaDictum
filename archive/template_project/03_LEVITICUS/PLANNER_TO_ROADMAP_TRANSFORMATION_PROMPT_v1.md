# PLANNER_TO_ROADMAP_TRANSFORMATION_PROMPT_v1

## 1. Role

Transform `01_GENESIS/PROJECT_SEED.md` into a roadmap that conforms exactly to
`03_LEVITICUS/ROADMAP_SCHEMA_v1.md`.

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
structural constraints that do not conflict with the required sections.

If required sections are missing: halt.

## 3. Transformation Rules

- Use only requirements present in the seed.
- Do not invent unstated requirements.
- Do not reference prior chat or external memory.
- Derive the minimal implementation phases needed to realize the seed.
- Do not assume a fixed application architecture such as frontend/backend,
  API/service, CLI, or batch processing unless the seed requires it.
- Do not assume specific filenames, frameworks, or runtimes unless the seed
  requires them.
- Do not blend phase objectives.

## 4. Output Contract

Output must:
- use exact phase structure and heading/order from
  `03_LEVITICUS/ROADMAP_SCHEMA_v1.md`
- use mechanically verifiable Entry Criteria and Exit Criteria
- use only structural, artifact-observable, or command-observable criteria
- contain no text outside schema-conforming roadmap content

If superseding an existing roadmap, include the revision metadata block
required by Section 8 of `03_LEVITICUS/ROADMAP_SCHEMA_v1.md` before Phase 1.

## 5. Phase Construction Rules

- Phase 1 is mandatory.
- Phase 1 must create at least one concrete artifact required by the seed.
- At least one Phase 1 Exit Criterion must prove that artifact using an exact
  workspace-relative path plus an exact anchor string or other allowed
  criterion form from the schema.
- Every later phase must depend only on earlier declared artifacts, explicit
  commands, or seed-defined constraints.
- If the seed Success Definition includes executable outcomes, map them into
  schema-valid command criteria rather than qualitative statements.

If these rules cannot be satisfied from the seed: halt.

## 6. Prohibitions

- No qualitative completion language.
- No additional sections.
- No validation commentary.
- No completion claims.
- No domain-specific hard-coding not grounded in the seed.
