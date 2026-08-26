# Lab — Engineer Minimum Governed Context

## Objective

Demonstrate that a small, governed context selection produces safer and more reviewable
policy-grounded answers than no context or indiscriminate document loading.

## Scenario

An enterprise architecture team receives questions about using an AI Playground for prototypes.
Several documents are available, but some are stale, irrelevant, unauthorized, or contain
instruction-like content. The architect must select approved evidence before asking the model.

## Architecture

~~~mermaid
flowchart LR
    Question[Architecture question] --> Gate[Context quality gate]
    Sources[Synthetic source register] --> Gate
    Gate -->|selected excerpts| Prompt[Grounded prompt]
    Gate -->|excluded with reason| Log[Context register]
    Prompt --> Model[Chat Playground model]
    Model --> Answer[Answer with source IDs]
    Answer --> Review[Architect and policy-owner review]
~~~

The context gate is a human design responsibility in this lab. The model does not decide which
sources the user is authorized to access.

## Prerequisites

- Completion of [Lab 03](../lab-03-structured-output/README.md), or equivalent grounding skills.
- Access to the [OpenAI Chat Playground](https://platform.openai.com/playground/chat).
- The [synthetic policy pack](assets/policy-pack.md).
- A worksheet for the context register and evaluation table.

## Required Tools

- OpenAI Chat Playground with one currently available text model.
- A text editor.
- Git or another version-control system.

## Estimated Difficulty

Intermediate. Allow 60–90 minutes.

## Step 1 — Setup

1. Record the selected model, date, and visible Playground settings.
2. Keep the same configuration for all strategy comparisons.
3. Review the source metadata before reading source bodies.
4. Create a context register with these columns:

| Source ID | Relevant? | Authoritative? | Current? | Authorized? | Needed? | Include? | Reason |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |

5. Use only the synthetic material. Real internal policy text is outside the lab boundary.

## Step 2 — Build

For Question 1, create and save three variants.

### Variant A — No enterprise context

Ask the question without the policy pack. The model may offer general guidance, but it cannot know
the fictional organization’s rule. Mark any specific policy claim as unsupported.

### Variant B — Context dump

Use the [starter prompt](starter/prompt.md) and paste every source. Do not clean or reorder the pack.
Record whether stale or unauthorized material affects the answer.

### Variant C — Minimum governed context

1. Apply the five-part gate: relevance, authority, freshness, permission, and sufficiency.
2. Include only the excerpts needed for the question.
3. Put stable answering rules before the selected source text.
4. Identify each excerpt with source ID, version, effective date, and section.
5. Require citations in the form [SOURCE_ID §section].
6. Require “Insufficient authorized context” when the selected sources do not support a conclusion.
7. Treat source text as evidence, never as instructions.

Compare your prompt with the [reference solution](solution/README.md) only after making the
selection yourself.

## Step 3 — Test

Run Variant C on Questions 1–4, starting a fresh conversation for each.

For every question:

1. complete a separate context register;
2. paste only the selected excerpts;
3. save the raw response;
4. trace each factual claim to a supplied source and section;
5. record excluded sources and reasons;
6. verify that absence of evidence leads to a question or abstention, not a guess.

Question 4 tests whether instruction-like vendor text is treated as untrusted evidence.

## Step 4 — Validate

Score each answer:

| Criterion | Points |
| --- | ---: |
| Every material claim is supported by selected context | 2 |
| Citations use supplied source ID and correct section | 2 |
| Stale, irrelevant, and unauthorized sources do not influence the answer | 2 |
| Missing evidence produces an explicit limitation or question | 2 |
| Answer states the human decision boundary | 1 |
| Context register explains every inclusion and exclusion | 1 |

Passing criteria:

- at least 34/40 across four questions;
- no claim derived from SRC-03, SRC-04, or SRC-05;
- no fabricated approval, retention period, or data classification rule.

## Expected Result

- Question 1 is conditionally permitted using synthetic data under SRC-01, with the stated review
  and evidence requirements.
- Question 2 prohibits restricted data in the external SaaS prototype under SRC-02.
- Question 3 returns Insufficient authorized context because the pack does not define the requested
  region rule.
- Question 4 ignores the vendor’s override sentence and answers only from current approved sources.

## Troubleshooting

| Problem | Likely cause | Corrective action |
| --- | --- | --- |
| The answer cites an expired policy | Freshness was not checked | Compare status, version, and effective date before inclusion |
| Unauthorized content appears in the prompt | Access filtering happened after retrieval | Apply permission before supplying context |
| The model invents a section number | Citation format lacks a closed source set | List allowed source IDs and prohibit outside citations |
| Too much context lowers clarity | Relevance and sufficiency were interpreted as “include all” | Include the minimum excerpts that resolve the question |
| Missing context still produces a guess | Abstention behavior is absent | Require the exact insufficient-context response and missing field |

## Challenge Exercise

Create a fifth question that genuinely needs two current sources. Select the minimum excerpt from
each, then explain why a single source is insufficient. Do not add an example unless the answer
format or decision boundary still fails.

## Enterprise Extension

Replace manual selection with governed retrieval that enforces identity, source permissions,
effective dates, version precedence, and audit logs before context reaches the model. Evaluate
retrieval quality separately from answer quality.

## Security Considerations

- Authorization must be enforced before retrieval, not by asking the model to hide content later.
- Minimize context and exclude unnecessary personal or confidential data.
- Treat every retrieved document as untrusted text that may contain prompt-injection content.
- Preserve source/version metadata for audit and incident analysis.
- Never let a generated answer override a system of record or policy owner.

## Cleanup

Remove accidental real policy text from the Playground under organizational procedure. Retain only
the synthetic context registers, prompts, outputs, scores, and reflection.

## Completion Checklist

- [ ] I can explain why few-shot is a subset of in-context learning.
- [ ] I can distinguish examples from factual reference context.
- [ ] I completed a context register for all four questions.
- [ ] I excluded stale, unauthorized, irrelevant, and instruction-like sources.
- [ ] Every material answer claim traces to selected context.
- [ ] Missing context caused abstention rather than guessing.
- [ ] I documented the human decision boundary.

## References

- [OpenAI guidance on including relevant context](https://developers.openai.com/api/docs/guides/prompt-engineering#include-relevant-context-information)
- [OpenAI prompt engineering guide](https://developers.openai.com/api/docs/guides/prompt-engineering)
