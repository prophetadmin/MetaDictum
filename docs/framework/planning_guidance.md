# MetaDictum Planning Guidance

This document is advisory guidance, not an execution contract.

MetaDictum can bootstrap from incomplete inputs, but planning quality improves
when the project is already defined well enough to execute rather than still
being discovered.

## What To Front-Load

Put real project facts in place before roadmap generation whenever possible.

That usually includes:

- runtime and platform assumptions
- external dependencies and system boundaries
- storage, schema, or data-shape facts
- service addresses, ports, and integration details
- hardware or environment constraints
- model identities or other fixed technical dependencies

The point is not paperwork. The point is to avoid using the roadmap as a place
to discover basic project facts that were already knowable.

## What `IDEA.md` Should Cover

[01_GENESIS/IDEA.md](https://github.com/prophetadmin/MetaDictum/blob/main/template/project/01_GENESIS/IDEA.md) does not need to be exhaustive, but it should be concrete enough to support clean bootstrap.

A good `IDEA.md` usually states:

- the problem being solved
- the intended user or audience
- the desired outcome
- the main constraints
- the obvious non-goals

If those basics are missing, bootstrap can still proceed, but the planning
artifacts will usually need more correction later.

## Practical Standard

Use the roadmap to execute an adequately defined project.

Do not rely on the roadmap to discover the project unless you are willing to
pay for that in revisions, clarification work, and roadmap churn.

## Tradeoff

Weak inputs do not make MetaDictum nondeterministic. They make the project less
prepared at planning time.

In practice:

- stronger inputs reduce roadmap revisions
- better technical context reduces drift and rework
- weaker inputs push discovery and correction into the planning surface
