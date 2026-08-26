# Lab 05 — Select, Debug, and Defend the Prompting Strategy

Use the OpenAI Chat Playground to choose the smallest effective strategy for eight enterprise
scenarios, test three of them, and defend each decision with evidence.

The central correction is important:

- **Zero-shot** and **few-shot** describe whether completed examples are present.
- **In-context learning** is the broader behavior of adapting from information in the current
  request or conversation.
- Few-shot prompting is therefore one kind of in-context learning.
- For method selection, this lab uses **context-grounded prompting** to mean supplying reference
  facts, policies, or conversation state rather than completed demonstrations.

## Learning outcomes

After this lab, you can:

- select zero-shot, few-shot, context-grounded, or combined prompting by task shape;
- identify cases where prompting alone is not an adequate control;
- change one prompt variable at a time and keep a version log;
- compare strategies with representative tests and explicit thresholds;
- stop adding context when a shorter prompt already passes.

## Scenario

You are an AI engineer reviewing proposed prompts from business analysts, project managers,
developers, solution architects, and RPA teams. Your job is to recommend a method, evidence plan,
and human boundary—not the most elaborate prompt.

## Evidence produced

- a completed eight-scenario decision matrix;
- three baseline/candidate Playground comparisons;
- a version and error log;
- a final strategy recommendation with limitations.

## Lab files

- [Detailed instructions](instructions.md)
- [Strategy decision record](starter/decision-record.md)
- [Reference decision guide and prompts](solution/README.md)
- [Enterprise scenario suite](assets/scenario-suite.md)

## Support boundary

The lab evaluates informational model responses only. It does not authorize external communication,
payments, access changes, production decisions, or other consequential actions.

[Previous lab](../lab-04-context-engineering/README.md) · [Back to Level 1 labs](../README.md)
