# Lab 01 — Build a Zero-Shot Baseline

Use the OpenAI Chat Playground to turn a vague business-analysis request into a controlled
zero-shot prompt, then measure whether the revised prompt is more complete and faithful.

Zero-shot does **not** mean “no input” or “no context.” It means the prompt contains no completed
input/output examples for the model to imitate. The prompt may still contain a role, task data,
constraints, and an output contract.

## Learning outcomes

After this lab, you can:

- recognize a true zero-shot prompt;
- decide when instructions alone are sufficient;
- separate task instructions from the business input;
- keep the same model and settings while comparing prompt versions;
- score completeness, grounding, and format adherence with a repeatable rubric.

## Scenario

You are a business analyst converting synthetic stakeholder notes into a requirements brief. The
task is familiar and the required sections can be described directly, so zero-shot is the smallest
reasonable starting technique.

## Evidence produced

- the raw baseline response;
- your engineered zero-shot response;
- a completed score for all three test cases;
- a short decision explaining whether examples are necessary.

## Lab files

- [Detailed instructions](instructions.md)
- [Starter prompt](starter/prompt.md)
- [Reference solution](solution/README.md)
- [Synthetic test cases and answer key](assets/test-cases.md)

## Support boundary

This is a prompt-only educational lab. It does not call tools or change business records. Model
output is probabilistic, so wording may differ while still passing the rubric. Record the model
identifier and run date with your evidence.

[Back to Level 1 labs](../README.md)
