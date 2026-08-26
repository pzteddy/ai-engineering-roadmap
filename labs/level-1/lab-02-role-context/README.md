# Lab 02 — Teach Custom Boundaries with Few-Shot Examples

Use the OpenAI Chat Playground to classify project updates with an organization-specific three-label
policy. Compare direct instructions with a few-shot prompt and measure exact-label accuracy.

Few-shot prompting is a form of **in-context learning**: completed examples are placed in the
current prompt so the model can infer and apply their pattern. Few-shot is useful when examples
communicate a boundary more efficiently than additional prose.

## Learning outcomes

After this lab, you can:

- explain why few-shot is a subset of in-context learning;
- choose examples that cover meaningful decision boundaries;
- keep examples separate from the new test input;
- detect example leakage, class imbalance, and accidental label changes;
- compare zero-shot and few-shot prompts on the same test set.

## Scenario

A project management office uses the labels ON_TRACK, AT_RISK, and BLOCKED. Ordinary language is
not precise enough to guarantee that every team applies these labels consistently, so representative
examples demonstrate the local policy.

## Evidence produced

- zero-shot and few-shot predictions for six cases;
- two accuracy totals;
- an error analysis for every mismatch;
- an example-selection rationale.

## Lab files

- [Detailed instructions](instructions.md)
- [Starter zero-shot classifier](starter/prompt.md)
- [Reference few-shot solution](solution/README.md)
- [Synthetic policy, examples, and test set](assets/status-cases.md)

## Support boundary

The classifier supports human reporting; it does not change project status in any system. A project
owner remains accountable for the official status.

[Previous lab](../lab-01-basic-prompt/README.md) · [Back to Level 1 labs](../README.md)
