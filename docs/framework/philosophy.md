# MetaDictum Philosophy

MetaDictum treats the repository as the durable system of record for
AI-assisted project execution.

The core principle is:

- files hold project state
- models are stateless processors

Persistent continuity must live in artifacts stored in the repository. Chat
output is temporary reasoning space, not authority.

This design exists to address the main weakness of AI-assisted development:
limited context windows and unreliable session continuity.

MetaDictum is intended for projects where continuity, reproducibility, and
auditability matter more than raw speed. It is aimed at multi-session,
artifact-governed work rather than disposable one-shot generation.

The framework separates project truth into filesystem layers so different kinds
of information do not collapse into one mixed working memory:

- `01_GENESIS/` for ideation and seed material
- `02_EXODUS/` for implementation work
- `03_LEVITICUS/` for governance artifacts, prompts, schemas, roadmaps, state,
  and canonical phase completion receipts
- `04_DEUTERONOMY/` for optional distilled canon
- `05_NUMBERS/` for optional historical and session summaries

Bootstrap determinism is layered on purpose:

- seed normalization (`PROJECT_SEED.md`)
- requirements normalization (`REQUIREMENTS_LEDGER.md`)
- component realization mapping (`COMPONENT_REALIZATION_MAP.md`)
- roadmap synthesis (`PROJECT_ROADMAP_v<INTEGER>.md`)

Execution determinism is receipt-aware by design. A phase is not complete
until required exit criteria and the canonical phase receipt criteria are both
satisfied.

The template boundary is intentional. The project template is an execution
surface for agents and should remain as sterile as practical. Framework
philosophy, planning advice, and explanatory prose belong outside the template
so they do not pollute the operational workspace.

Determinism in MetaDictum is mechanical, not magical. The framework can execute
consistently against whatever artifacts it is given. Better outcomes still
depend on better inputs.

Optional commands such as session summarization and canon extraction extend the
framework without becoming mandatory runtime bureaucracy:

- `05_NUMBERS/` may be used to preserve high-signal session summaries
- `04_DEUTERONOMY/` may be populated later through canon extraction

Neither is required for basic execution. Both exist to improve continuity and
distillation when the user wants them.

Deuteronomy is best treated as a conclusions layer rather than an actively
maintained mirror of the project. Canon may be extracted after the project is
finished or stabilized. It does not need to be maintained continuously during
execution.
