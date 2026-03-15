# MetaDictum

MetaDictum is a filesystem-authoritative framework for deterministic, multi-session AI-assisted project execution. It preserves project continuity in repository artifacts rather than fragile chat context.

This repository contains the framework documentation and reusable project template that implement that workflow.

The operational scaffold lives in `template/project/`.

## Why MetaDictum Exists

- AI-assisted project work often loses continuity across sessions.
- MetaDictum keeps project state in repository artifacts instead of chat memory.
- That makes planning, execution, handoff, and resumption more deterministic.

## Workspace Model

MetaDictum uses a five-domain workspace model:

- `01_GENESIS/` — project intent and seed artifacts
- `02_EXODUS/` — active implementation workspace
- `03_LEVITICUS/` — governance, roadmap, and execution state
- `04_DEUTERONOMY/` — canonical or promoted outputs
- `05_NUMBERS/` — logs, reports, and operational records

## Repository Contents

- `template/project/` contains the reusable project template and execution surface
- `docs/framework/` contains framework documentation

## Documentation

- `docs/framework/quickstart.md`
- `docs/framework/philosophy.md`
- `docs/framework/lifecycle.md`
- `docs/framework/planning_guidance.md`