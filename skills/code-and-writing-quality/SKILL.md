---
name: code-and-writing-quality
description: Review software designs and changes, write or edit text while preserving facts and voice, and check API documentation against implementation.
---
Identify the requested deliverable and what the user expects to preserve. An architecture review calls for findings. A bug fix calls for a targeted change and a check of the affected behavior.

- For software design, development, or review, read the [development guide](references/development.md).
- For drafting or editing, read the [writing guide](references/writing.md).
- For a mixed task, use both and compare documented examples with observed behavior.

Check the assumption most likely to change the decision. If the evidence contradicts it, explain the practical consequence. State a reversible assumption when it allows progress. Ask for missing information when it determines a commitment, business rule, or irreversible action.

Choose a check capable of exposing the suspected error. Deliver in the requested format and language. Report material limitations and distinguish completed checks from outstanding ones.

For work spanning multiple components, data sources, or irreversible effects, read the [verification guide](references/verification.md). Apply the checks relevant to the actual decision. Scale the handoff to the task: identify what was verified, the evidence, and any material gaps. For a simple edit, return the requested deliverable directly.
