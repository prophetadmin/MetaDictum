# /validate_map_v2 Prompt

Command Name
/validate_map_v2

Purpose
Validate a roadmap artifact against `03_LEVITICUS/ROADMAP_SCHEMA_v2.md` and
seed-coverage requirements so roadmap acceptance cannot pass on documentation-only
implementation criteria.

Required Inputs
`01_GENESIS/PROJECT_SEED.md`
`03_LEVITICUS/ROADMAP_SCHEMA_v2.md`
`03_LEVITICUS/FAILURE_CODES_v1.md`
`03_LEVITICUS/PROJECT_ROADMAP_v<INTEGER>.md` (target)

Validation Checks (All Required)
1. Schema structure and subsection order exactly match v2 schema.
2. Phase identifiers are monotonically increasing integers starting at 1.
3. Required `Seed Coverage Matrix` exists and maps:
   - all seed Scope Boundaries Included items
   - all seed Constraints items
   to concrete phase Exit Criteria.
4. At least one phase has `Phase Type` = `implementation`.
5. At least one phase has `Phase Type` = `validation`.
6. Every `implementation` phase includes:
   - at least one command-based Exit Criterion
   - at least one non-documentation produced artifact
   - at least one non-dry-run command criterion
7. No implementation phase can complete using only `.md` file-exists and anchor
   checks.
8. Validation phase includes at least one command criterion that exercises the
   end-to-end system path implied by the seed problem and included scope.
9. Roadmap does not invent command/path/framework conventions unless grounded in
   seed or explicitly allowed in policy.

Failure Contract
- Structural or grammar failure: `SCHEMA_VIOLATION`
- Missing architecture or coverage mapping: `ARCHITECTURE_COVERAGE_FAILURE`
- Unseeded command/path/runtime assumptions: `SCOPE_VIOLATION`

Output Contract
Emit only one of:
- `PASS`
- `FAIL <CODE>: <single-line reason>`
