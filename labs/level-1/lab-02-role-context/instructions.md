# Lab — Teach Custom Boundaries with Few-Shot Examples

## Objective

Determine whether few-shot examples improve exact classification accuracy for a custom project
status policy.

## Scenario

Different project managers use “risk” and “blocked” inconsistently. The PMO needs a review assistant
that assigns exactly one policy label from a short weekly update. The assistant recommends a label;
the project owner confirms it.

## Architecture

~~~mermaid
flowchart LR
    Policy[Label policy] --> Prompt[Instructions]
    Examples[Completed examples] --> Prompt
    Update[New project update] --> Prompt
    Prompt --> Model[Chat Playground model]
    Model --> Label[One proposed label]
    Label --> Compare[Compare with answer key]
    Compare --> Owner[Project owner review]
~~~

The examples teach label boundaries inside the current request. They do not update model weights.

## Prerequisites

- Completion of [Lab 01](../lab-01-basic-prompt/README.md), or equivalent prompt-baseline skills.
- An approved OpenAI Platform account and access to the
  [Chat Playground](https://platform.openai.com/playground/chat).
- The [synthetic status cases](assets/status-cases.md).

## Required Tools

- OpenAI Chat Playground and one available text model.
- A worksheet using the results table in the assets file.
- Git or another version-control system for the prompt versions.

## Estimated Difficulty

Beginner to intermediate. Allow 45–60 minutes.

## Step 1 — Setup

1. Start a new Playground prompt.
2. Record the selected model, run date, and visible settings.
3. Keep model and settings fixed for both variants.
4. Copy the zero-shot [starter prompt](starter/prompt.md).
5. Read the label policy and answer key only far enough to understand the labels; do not paste the
   hidden test answers into the prompt.

## Step 2 — Build

### Variant A — Defined zero-shot

Use the starter prompt and run all six test updates. It includes definitions but no completed
examples.

### Variant B — Few-shot

Create a second version containing:

1. the same label definitions;
2. exactly one clear example per label;
3. diverse signals rather than three near-duplicate examples;
4. the exact desired assistant response for each example;
5. the new update in a separate TEST_UPDATE block.

Put reusable instructions and examples in a high-priority instruction message when the Playground
supports message roles. Put only the new update in the user message. The
[reference solution](solution/README.md) shows one correct arrangement.

Do not add the six test cases as examples. That would leak the answer key.

## Step 3 — Test

For each prompt variant:

1. Start a fresh conversation for each test case.
2. Paste one test update with no expected label.
3. Run once and record the exact response.
4. Mark a pass only when the response is exactly ON_TRACK, AT_RISK, or BLOCKED and matches the key.
5. Record extra commentary as a format failure even when the label is correct.

Complete both six-row result tables before changing the prompt. Do not selectively rerun only the
mistakes and report the best answer.

## Step 4 — Validate

Calculate exact-label accuracy:

~~~text
accuracy = correct labels / 6
~~~

The lab passes when:

- the few-shot prompt scores at least 5/6;
- it never returns a label outside the allowed set;
- it is at least as accurate as the defined zero-shot prompt;
- each example has a written reason for inclusion;
- no test answer appears in the prompt.

If zero-shot already scores 6/6, the valid conclusion may be that few-shot is unnecessary for this
model and test set. Do not claim improvement where none was measured.

## Expected Result

The few-shot prompt should make the local boundary clearer: work that can continue but threatens a
commitment is AT_RISK; work that cannot continue because of an unresolved dependency is BLOCKED.
The model should output only one allowed label.

## Troubleshooting

| Problem | Likely cause | Corrective action |
| --- | --- | --- |
| All outputs copy one example label | Examples are imbalanced or too similar | Use one clear, diverse example per class |
| The model explains its answer | Example outputs contain explanations or output rule is weak | Demonstrate and require a single-token label |
| AT_RISK and BLOCKED are confused | Boundary is not observable | State whether work can continue, then show both boundary examples |
| Accuracy changes across variants unfairly | Model, settings, or cases changed | Restore the same configuration and test set |
| Test performance is perfect in both | Task is already instruction-solvable | Prefer zero-shot unless broader evaluation shows a few-shot benefit |

## Challenge Exercise

Add a fourth label, UNKNOWN, for updates that lack enough evidence to apply another label. Create
one representative example and two new tests. Explain why guessing ON_TRACK from silence is unsafe.

## Enterprise Extension

Move label definitions into an owned policy artifact. Version examples with the policy, require
representative cases from different teams, monitor label distribution, and review disagreements
between the assistant and project owners.

## Security Considerations

- Use synthetic updates in the public lab.
- Remove employee names, customer names, and confidential delivery details from real evaluations.
- Do not allow the model to publish or change project status automatically.
- Treat pasted updates as data, not as permission to override the label policy.
- Review examples for hidden bias toward a team, vendor, or writing style.

## Cleanup

Delete any accidental sensitive Playground content under the approved data-handling procedure.
Retain the synthetic prompts, unedited outputs, result tables, and analysis only.

## Completion Checklist

- [ ] I can explain that few-shot is a form of in-context learning.
- [ ] I tested the same six cases with both prompt variants.
- [ ] I used a fresh conversation for each case.
- [ ] My examples cover all three labels and their boundaries.
- [ ] I calculated exact-label accuracy honestly.
- [ ] I documented whether few-shot earned its additional prompt cost.
- [ ] A human remains the official project-status owner.

## References

- [OpenAI few-shot learning guidance](https://developers.openai.com/api/docs/guides/prompt-engineering#few-shot-learning)
- [OpenAI prompt engineering guide](https://developers.openai.com/api/docs/guides/prompt-engineering)
