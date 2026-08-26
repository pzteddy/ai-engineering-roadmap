# Lab 04 — Engineer Minimum Governed Context

Use the OpenAI Chat Playground to answer architecture-policy questions from a synthetic document
pack. Compare no context, indiscriminate context, and a minimum governed context selection.

This is another form of **in-context learning**, but it is not few-shot prompting: the prompt
contains reference facts rather than completed input/output demonstrations. The model adapts its
answer to information supplied for the current request.

## Learning outcomes

After this lab, you can:

- distinguish prompt instructions from factual context;
- select context for relevance, authority, freshness, permission, and sufficiency;
- exclude stale, unauthorized, and instruction-like source text;
- require grounded citations and safe missing-context behavior;
- explain when context and few-shot examples should be combined.

## Scenario

A solution architect must answer prototype data-handling questions from a fictional policy pack.
The model drafts an answer; the policy owner and architect remain responsible for decisions.

## Evidence produced

- answers from three context strategies;
- a completed context register for each question;
- groundedness and citation scores;
- a missing-context response and an exclusion rationale.

## Lab files

- [Detailed instructions](instructions.md)
- [Starter context-dump prompt](starter/prompt.md)
- [Reference selection and prompt solution](solution/README.md)
- [Synthetic policy pack and questions](assets/policy-pack.md)

## Support boundary

All policy documents are synthetic and have no authority outside this lab. Do not use the reference
answers as legal, privacy, security, or organizational advice.

[Previous lab](../lab-03-structured-output/README.md) · [Back to Level 1 labs](../README.md)
