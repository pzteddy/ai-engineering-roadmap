# Lab — Select, Debug, and Defend the Prompting Strategy

## Objective

Choose the smallest effective prompting method for eight scenarios and demonstrate, through
controlled Playground comparisons, that three selected methods meet their success criteria.

## Scenario

An AI enablement team receives requests that sound similar—“make the answer better”—but fail for
different reasons. Some need clearer instructions, some need examples, some need governed facts, and
some require controls outside the prompt.

## Architecture

~~~mermaid
flowchart TD
    Task[Define task and success criteria] --> Facts{Needs current or private facts?}
    Facts -->|Yes| Context[Add minimum governed context]
    Facts -->|No| Pattern{Custom pattern or boundary unclear?}
    Pattern -->|Yes| FewShot[Add representative examples]
    Pattern -->|No| ZeroShot[Start zero-shot]
    Context --> Pattern
    FewShot --> Eval[Test representative cases]
    ZeroShot --> Eval
    Eval --> Pass{Meets threshold?}
    Pass -->|No| Diagnose[Classify the failure and change one variable]
    Diagnose --> Task
    Pass -->|Yes| Consequence{Consequential action?}
    Consequence -->|Yes| Controls[Add deterministic authorization and human approval]
    Consequence -->|No| Version[Version the smallest passing prompt]
~~~

The decision tree chooses a starting method. Evaluation decides whether the method is sufficient.

## Prerequisites

- Completion of Labs [01](../lab-01-basic-prompt/README.md),
  [02](../lab-02-role-context/README.md),
  [03](../lab-03-structured-output/README.md), and
  [04](../lab-04-context-engineering/README.md), or equivalent skills.
- Access to the [OpenAI Chat Playground](https://platform.openai.com/playground/chat).
- The [scenario suite](assets/scenario-suite.md).

## Required Tools

- OpenAI Chat Playground with one available text model.
- A text editor and the [decision record](starter/decision-record.md).
- Git or another versioning method.

## Estimated Difficulty

Intermediate. Allow 90–120 minutes.

## Step 1 — Setup

1. Copy the decision record into your working notes.
2. Record the model, run date, and visible settings.
3. Keep the same configuration within each baseline/candidate comparison.
4. Read all eight scenarios without reading the reference solution.
5. For each scenario, write the task, required evidence, risk, and pass criteria before selecting a
   prompting method.

## Step 2 — Build

### Part A — Select methods

Choose one starting recommendation for every scenario:

- zero-shot;
- few-shot;
- context-grounded zero-shot;
- context-grounded plus few-shot;
- prompting is insufficient without an external control.

Do not select “in-context learning” as though it were mutually exclusive with few-shot. Instead,
name which information is supplied in context: demonstrations, reference facts, or conversation
state.

### Part B — Build three comparisons

Choose:

1. one scenario you classified as zero-shot;
2. one scenario you classified as few-shot;
3. one scenario you classified as context-grounded.

For each, create:

- **v0 baseline:** the shortest vague request in the scenario;
- **v1 candidate:** your selected method with explicit success criteria;
- a test set with at least three variations;
- a scoring table.

Keep a version log. Change only one logical variable between versions—for example, examples,
reference context, or output contract. If several elements change together, you cannot attribute
the result.

### Part C — Compare with the reference

After completing your decisions and v1 prompts, read the
[reference solution](solution/README.md). Revise only where the reference exposes a failure your
tests did not cover.

## Step 3 — Test

For every selected scenario:

1. run v0 and v1 on the same three tests;
2. start a fresh conversation for each independent test;
3. save every raw output;
4. score against scenario-specific facts and format criteria;
5. label failures as instruction, example, context, format, grounding, safety, or missing-control;
6. create v2 only if v1 fails, and state the single change.

Do not keep rerunning until a preferred answer appears. If variability matters, predeclare a repeat
count and report every run.

## Step 4 — Validate

The lab passes when:

- all eight scenario choices match the scenario’s information need and consequence;
- all three candidate prompts score at least 85% on their declared rubric;
- no candidate invents current/company facts;
- the selected few-shot prompt uses representative, non-leaking examples;
- the context-grounded prompt excludes unauthorized or irrelevant material;
- the consequential scenario identifies non-prompt controls;
- the final recommendation chooses the shortest prompt that meets the threshold.

Your decision record must contain at least one case where **not** adding examples is the correct
choice.

## Expected Result

You should not finish with one universally “best” method. You should finish with a routing rule:

- start zero-shot for clear, familiar tasks;
- add few-shot demonstrations for custom patterns or hard-to-describe boundaries;
- add minimum governed reference context when the answer depends on supplied facts;
- combine them only when both knowledge and behavior need steering;
- add deterministic controls and human approval when consequences exceed an informational answer.

## Troubleshooting

| Problem | Likely cause | Corrective action |
| --- | --- | --- |
| Every scenario is marked few-shot | Examples are being treated as a generic quality boost | Identify the specific boundary each example teaches |
| “In-context” is selected as a third exclusive category | Mechanism and prompt technique are mixed | Name the context type: demonstrations, facts, or conversation state |
| Candidate improvement cannot be explained | Too many variables changed | Revert and change one logical element per version |
| Current facts are invented | The task needs retrieval or supplied context | Add governed current evidence or abstain |
| High-risk action is “secured” only by wording | Prompting is being used as authorization | Add deterministic policy, identity, approval, and audit controls |

## Challenge Exercise

Create two prompts for the same support task:

- a context-grounded zero-shot version with explicit tone rules;
- a context-grounded few-shot version with two house-style examples.

Evaluate whether examples create a measurable style gain. If not, remove them and explain the cost
and maintenance benefit.

## Enterprise Extension

Create a prompt registry containing use case, owner, prompt version, context sources, example-set
version, model/config, evaluation-set version, thresholds, approved data classes, limitations, and
review date. Require regression evidence before changing any of those components in production.

## Security Considerations

- Never use prompt text as a substitute for authentication, authorization, or approval.
- Apply source permissions before adding context.
- Treat examples and reference documents as potentially biased or malicious inputs.
- Do not expose sensitive data in evaluation evidence.
- Require human review proportional to business consequence.

## Cleanup

Remove accidental sensitive Playground content according to policy. Keep synthetic prompts, raw
outputs, scores, version logs, and the final strategy decision. No credentials should be stored.

## Completion Checklist

- [ ] I selected a method for all eight scenarios before reading the solution.
- [ ] I can explain why few-shot is a kind of in-context learning.
- [ ] I tested zero-shot, few-shot, and context-grounded candidates.
- [ ] I changed one logical variable per prompt version.
- [ ] All three candidates met the declared threshold.
- [ ] I selected at least one zero-shot prompt as the best final method.
- [ ] I identified where prompting alone is insufficient.
- [ ] I documented security and human decision boundaries.

## References

- [OpenAI prompt engineering guide](https://developers.openai.com/api/docs/guides/prompt-engineering)
- [OpenAI model prompting best practices](https://developers.openai.com/api/docs/guides/latest-model#prompting-best-practices)
