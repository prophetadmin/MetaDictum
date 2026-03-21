# MetaDictum

MetaDictum is a filesystem-authoritative framework for deterministic,
multi-session AI-assisted project execution. It preserves project continuity in
repository artifacts rather than fragile chat context.

This repository contains the framework documentation and reusable project
template that implement that workflow.

**Version:** v2.0  
MetaDictum v2 introduces runtime hardening for deterministic execution,
including receipt-gated phase completion, explicit phase advancement, and
repository-state-neutral execution semantics.

**Execution exemplar:** [ARGUS](https://github.com/prophetadmin/Argus)
demonstrates the framework applied to a non-trivial project from bootstrap
through validation, with repository artifacts preserved as execution evidence.

The operational scaffold lives in
[template/project/](https://github.com/prophetadmin/MetaDictum/tree/main/template/project).

## Why MetaDictum Exists

- AI-assisted project work often loses continuity across sessions.
- MetaDictum keeps project state in repository artifacts instead of chat memory.
- That makes planning, execution, handoff, and resumption more deterministic.

## Workspace Model

MetaDictum uses a five-domain workspace model:

- `01_GENESIS/` - project intent and bootstrap planning artifacts
- `02_EXODUS/` - active implementation workspace
- `03_LEVITICUS/` - governance, roadmap, execution state, and receipts
- `04_DEUTERONOMY/` - canonical or promoted outputs
- `05_NUMBERS/` - logs, reports, and operational records

## Repository Contents

- `template/project/` contains the reusable project template and execution
  surface
- `docs/framework/` contains framework documentation

## Documentation

- [docs/framework/quickstart.md](https://github.com/prophetadmin/MetaDictum/blob/main/docs/framework/quickstart.md)
- [docs/framework/philosophy.md](https://github.com/prophetadmin/MetaDictum/blob/main/docs/framework/philosophy.md)
- [docs/framework/lifecycle.md](https://github.com/prophetadmin/MetaDictum/blob/main/docs/framework/lifecycle.md)
- [docs/framework/planning_guidance.md](https://github.com/prophetadmin/MetaDictum/blob/main/docs/framework/planning_guidance.md)

## v2.0 Runtime Hardening

- Introduced receipt-gated phase completion
- Eliminated pre-existing artifact auto-completion
- Enforced explicit phase advancement via runtime prompts
- Added repository-state-neutral execution semantics
