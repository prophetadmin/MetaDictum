# MetaDictum Planning Guidance

This document is human guidance, not an execution contract.

MetaDictum can run with weak inputs, but weak inputs usually produce weaker
roadmaps, more revisions, and more roadmap drift.

## Front-Load Real Context

If a project depends on real technical constraints or environment details, that
context should be supplied before roadmap generation whenever possible.

Useful front-loaded inputs may include:

- runtime and platform assumptions
- ports and endpoints
- schema details
- storage locations
- service addresses
- model identities
- collection names
- hardware constraints
- external system dependencies

The goal is not to burden the user with paperwork. The goal is to avoid using
the roadmap as a scratch pad for discovering facts that could have been stated
up front.

## Strong Ideas Produce Better Seeds

`IDEA.md` quality matters.

A strong idea artifact usually states:

- the problem or opportunity
- the intended user or audience
- the desired outcome
- relevant constraints
- non-goals

MetaDictum does not require perfect ideation to function. It will still execute
against incomplete inputs. But incomplete inputs often lead to frequent roadmap
revision and just-in-time clarification work.

## Garbage In -> Roadmap Drift

This is an advisory principle, not a contract rule.

If important facts are missing at roadmap-generation time, the roadmap will
still be generated, but it is more likely to absorb discovery work, correction
work, and replanning work that should have happened earlier.

That does not make the framework nondeterministic. It makes the project inputs
less prepared.

In practice:

- better inputs reduce roadmap churn
- stronger up-front context reduces versioning pressure
- weak inputs increase the chance that the roadmap becomes a correction surface
  instead of an execution surface

## Practical Standard

Use the roadmap to execute an adequately defined project whenever possible.

Do not rely on the roadmap itself to discover the project unless you accept the
cost of more revisions and drift correction later.
