# Level 1 Labs — Prompt & Context Engineering

The Level 1 track develops controlled, reusable AI tasks. AI returns information; the learner remains
responsible for verification and any business action.

## Planned lab sequence

| Lab | Capability | Verifiable result |
| --- | --- | --- |
| Basic prompt | Establish a simple baseline | Baseline cases and observed failure categories |
| Role and context | Add task role and governed facts | Measured improvement without unnecessary context |
| Structured output | Define and validate a JSON schema | Invalid outputs are rejected or safely repaired |
| Context engineering | Select relevant, authoritative, current, sufficient, authorized context | Context register and missing-context behavior |
| Prompt debugging | Version, evaluate, and improve a prompt | Candidate beats baseline without violating safety criteria |

## Integrated mini-project

Build an AI assistant for an enterprise knowledge task such as incident summarization, requirements
analysis, or document classification. It must use a versioned prompt contract, safe sample inputs,
validated output, and a small evaluation set.

## Completion gate

- The task, intended user, non-goals, and human decision boundary are explicit.
- Prompt, context, model/configuration, and expected output are versioned.
- Normal, edge, missing-context, and unsafe-input cases are evaluated.
- The assistant refuses or escalates when required information is missing.
- No automatic external or state-changing action occurs.

Previous: [Lab index](../README.md) · Next: [Level 2 labs](../level-2/README.md)
