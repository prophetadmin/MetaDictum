# MetaDictum Quick Start

This is the shortest canonical path to start and run a MetaDictum project.

## 1. Copy the template into a new project workspace

Start from:

[template/project/](https://github.com/prophetadmin/MetaDictum/tree/main/template/project)

Copy it into its own repository or workspace directory.

## 2. Open the copied project in your IDE

Open the new project root so the workspace-local `AGENTS.md` and prompt files
are active in that project.

## 3. Write the project idea

Write the project idea in:

[`01_GENESIS/IDEA.md`](https://github.com/prophetadmin/MetaDictum/blob/main/template/project/01_GENESIS/IDEA.md)

Keep it concrete. Define what you are building, who it is for, major
constraints, and obvious non-goals.

## 4. Run `/bootstrap`

Run:

`/bootstrap`

This is the canonical bootstrap entrypoint for a fresh or reset workspace.

It must execute this chain in order:

1. `/seed`
2. `/derive_requirements`
3. `/realize_components`
4. `/create_map_v2`
5. `/validate_map_v2`

Bootstrap is complete when these generated outputs exist:

- `01_GENESIS/PROJECT_SEED.md`
- `01_GENESIS/REQUIREMENTS_LEDGER.md`
- `01_GENESIS/COMPONENT_REALIZATION_MAP.md`
- `03_LEVITICUS/PROJECT_ROADMAP_v1.md`

## 5. Enter runtime correctly

Once a generated roadmap exists, the workspace is in Execution Mode.

Start runtime by running:

`/status_sync`

This emits the canonical phase-state summary into:

`03_LEVITICUS/STATE_SUMMARY.md`

## 6. Execute the active phase

Run:

`/resume_phase`

`/resume_phase` repeatedly runs `/resume` for the current Active Phase. When
the next unmet criterion is the canonical phase receipt criterion, it runs
`/record_phase_completion` before continuing. After the phase loop completes,
it runs `/status_sync` exactly once.

Use `/resume` directly only when you intentionally want single-step
deterministic advancement instead of phase-level continuation.

Use `/record_phase_completion` directly only when all non-receipt Exit
Criteria for the active phase are already directly proven and the next unmet
criterion is the canonical phase receipt.

## Runtime Loop

The normal operating pattern is:

1. `/status_sync`
2. `/resume_phase`
3. repeat for the next session or next phase

## Read Next

- [docs/framework/lifecycle.md](https://github.com/prophetadmin/MetaDictum/blob/main/docs/framework/lifecycle.md)
- [docs/framework/philosophy.md](https://github.com/prophetadmin/MetaDictum/blob/main/docs/framework/philosophy.md)
