# Level 1 Labs — Prompt & Context Engineering

The Level 1 track develops controlled, reusable AI tasks in the
[OpenAI Chat Playground](https://platform.openai.com/playground/chat). AI returns information; the
learner verifies it and remains responsible for every business decision or action.

> **Provider guidance reviewed:** 2026-08-26. Playground labels and model availability can change;
> each lab describes the control intent and requires learners to record the configuration they
> actually used.

## The terminology that matters

| Term | Precise meaning | Best starting scenario | Main caution |
| --- | --- | --- | --- |
| **Zero-shot** | Instructions and new task input with no completed examples | Clear, familiar tasks whose success criteria can be stated directly | A vague instruction is still vague even when called zero-shot |
| **Few-shot** | Instructions plus a small set of completed input/output demonstrations | Custom labels, house style, edge cases, or hard-to-describe boundaries | Examples consume context and can leak bias or teach the wrong pattern |
| **In-context learning** | The model adapts from information supplied in the current request or conversation | Umbrella mechanism for instructions, examples, reference facts, and conversation state | It is not a third technique mutually exclusive with few-shot |
| **Context-grounded prompting** | Instructions plus selected reference facts, policies, or documents | Answers that depend on current, private, or source-controlled knowledge | Context must be relevant, authoritative, current, sufficient, and authorized |

Few-shot prompting is one form of in-context learning. A policy-grounded answer is another use of
in-context learning, but its context supplies facts rather than demonstrations. A task may combine
reference context and few-shot examples when both knowledge and response behavior need steering.

## Quick selection guide

1. If the answer requires current, proprietary, or document-specific facts, supply the minimum
   governed reference context or retrieve it from an authorized source.
2. If the task is familiar and its output can be described clearly, start zero-shot.
3. If testing exposes a custom pattern, label boundary, tone, or edge case that prose does not
   control reliably, add representative few-shot examples.
4. If both facts and behavior are specialized, combine selected context with examples and evaluate
   whether each addition earns its cost.
5. If the task performs a consequential action, prompting is insufficient: add deterministic
   authorization, validation, human approval, and audit controls.

## Implemented lab sequence

| Lab | Primary capability | Verifiable result |
| --- | --- | --- |
| [01 — Zero-shot baseline](lab-01-basic-prompt/README.md) | Engineer a clear prompt without demonstrations | At least 13/15 rubric checks with no invented facts |
| [02 — Few-shot boundaries](lab-02-role-context/README.md) | Teach organization-specific labels with diverse examples | At least 5/6 exact labels and measured comparison with zero-shot |
| [03 — Structured JSON](lab-03-structured-output/README.md) | Define and validate a seven-key output contract | Valid JSON for every case and at least 17/18 contract checks |
| [04 — Governed context](lab-04-context-engineering/README.md) | Select relevant, authoritative, current, sufficient, authorized sources | At least 34/40 with grounded citations and safe abstention |
| [05 — Strategy and debugging](lab-05-prompt-debugging/README.md) | Route scenarios and improve one variable at a time | Eight justified selections and three candidates above 85% |

Each lab includes a complete learner workflow, safe synthetic assets, a deliberately limited starter,
a detailed reference solution, measurable validation, troubleshooting, enterprise extension,
security guidance, cleanup, and a completion checklist.

## Recommended order

Complete the labs in sequence. Lab 05 integrates evidence from the first four and directly answers
which technique is best for different enterprise scenarios.

For fair comparisons:

- record model identifier, date, and visible settings;
- keep configuration fixed within an experiment;
- use fresh conversations for independent tests;
- save raw responses rather than edited examples;
- report all declared runs, not only the best output.

## Integrated mini-project

After Lab 05, adapt one lab into a versioned assistant for incident summarization, requirements
analysis, or document classification. It must use safe inputs, an explicit human boundary,
validated output, a representative evaluation set, and a method-selection decision explaining why
zero-shot, few-shot, context-grounded, or combined prompting is appropriate.

## Completion gate

- The task, intended user, non-goals, and human decision boundary are explicit.
- Prompt, examples, context, model/configuration, and expected output are versioned when used.
- Normal, edge, missing-context, and instruction-like input cases are evaluated.
- The assistant refuses or escalates when required evidence is missing.
- No automatic external or state-changing action occurs.
- The selected technique is the smallest one that meets the evaluation threshold.

Previous: [Lab index](../README.md) · Next: [Level 2 labs](../level-2/README.md)
