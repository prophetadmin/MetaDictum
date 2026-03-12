# ROADMAP SCHEMA v1 - Canonical Phase Template

## 1. Scope

This schema defines the required structure for any roadmap generated into
`03_LEVITICUS/PROJECT_ROADMAP_v<INTEGER>.md`.

The schema is project-agnostic.
It must not assume a specific application type, language, framework, runtime,
or directory layout beyond the canonical project root described below.

## 2. Canonical Path Resolution

The canonical project root is the directory that contains:
- `01_GENESIS/`
- `02_EXODUS/`
- `03_LEVITICUS/`

All artifact paths in a roadmap MUST be written as workspace-relative paths from
that project root.

## 3. Phase Block - Required Structure

Each phase MUST conform to the exact block structure defined below.
No additional top-level headings are permitted inside a phase block.
Headings are case-sensitive.
Order is fixed and non-reorderable.

### PHASE <IDENTIFIER> - <TITLE>

**Purpose**
<Single-paragraph structural objective statement. No qualitative claims.>

**Inputs (Required)**
- <Artifact or dependency identifier>
- <Artifact or dependency identifier>

**Entry Criteria (All Required)**
- <Mechanically verifiable condition>
- <Mechanically verifiable condition>

**Work Definition (Scope-Bound)**
- <Concrete action>
- <Concrete action>

**Exit Criteria (All Required)**
- <Mechanically verifiable structural condition>
- <Mechanically verifiable structural condition>

**Produced Artifacts**
- <Artifact path>
- <Artifact path>

**Failure Signals**
- <Observable structural failure condition>
- <Observable structural failure condition>

## 4. Structural Constraints

1. A phase block MUST begin with:
   `### PHASE <IDENTIFIER> - <TITLE>`

2. `<IDENTIFIER>` MUST be a monotonically increasing integer starting at 1.

3. All bolded subsection headings inside a phase block are mandatory and must
   appear exactly once.

4. No subsection may contain freeform narrative outside its defined purpose.

5. Exit Criteria MUST define structural, observable, or executable conditions.
   They MUST NOT reference:
   - satisfaction
   - quality
   - adequacy
   - logical soundness
   - review status
   - subjective completeness

6. Completion of a phase is defined strictly as all Exit Criteria evaluating
   TRUE under direct inspection.

## 5. Criteria Grammar

### 5.1 Allowed Entry/Exit Criterion Forms

A criterion MUST conform to one of the following forms:

1. Artifact Exists
   `File exists at <workspace-relative path>.`

2. Artifact Contains Anchor
   `<File path> contains the exact anchor string: "<string>".`

3. Structure Present
   `<File path> contains heading: "<heading text>".`

4. Count Condition
   `<File path> contains exactly <N> instances of "<string>".`

5. Enumeration Complete
   `All required subsections defined in Section 3 are present exactly once.`

6. Deterministic Mapping
   `<Artifact A> is generated strictly from <Artifact B> without schema deviation.`

7. Command Exit Code
   `Command "<command>" exits with code <N>.`

8. Command Output Anchor
   `Command "<command>" exits with code <N> and emits "<anchor>" in <stream or output path>.`

### 5.2 Disallowed Criterion Forms

A criterion is INVALID if it:
- uses qualitative adjectives
- uses verbs such as "reviewed", "validated", "confirmed", or "looks correct"
- depends on human interpretation without structural anchor
- references external unstated memory

Invalid criteria invalidate the phase.

## 6. Phase Completion Rule

A phase is COMPLETE if and only if:
- every Exit Criterion evaluates TRUE

If any Exit Criterion is unmet, the phase remains ACTIVE.

`Produced Artifacts` declares the artifacts expected to be created or updated by
the phase. Any artifact whose existence is required for completion must also be
expressed explicitly in `Exit Criteria`.

`Failure Signals` are diagnostic indicators for validation and drift handling.
They do not add independent completion conditions unless a phase explicitly
anchors them through `Exit Criteria`.

No qualitative declaration such as "done", "complete", or "satisfactory" has
any effect on phase state.

## 7. Schema Authority

This document defines `ROADMAP_SCHEMA_v1`.

Any roadmap used by this workflow framework MUST conform exactly to this
schema. Deviation from required headings, required order, criteria grammar,
path resolution rules, or the phase completion rule constitutes schema
violation.

Schema changes require:
- explicit version increment
- documented delta section appended to this file

No planner, agent, or resume protocol may redefine or extend this schema
implicitly.

## 8. Revision Metadata Rule (When Superseding Existing Roadmap)

If a roadmap revision supersedes an existing roadmap artifact, the revised
roadmap MUST include a top metadata block before Phase 1:

**Roadmap Version**
<Version identifier, for example: v1, v2>

**Supersedes**
<Prior roadmap version identifier or `None`>

**Revision Rationale**
<Short structural reason for revision>

When generating an initial roadmap, `Supersedes` should be `None`.
The initial roadmap version must be `v1`.
The active roadmap artifact is the highest available
`03_LEVITICUS/PROJECT_ROADMAP_v<INTEGER>.md` by integer version.
