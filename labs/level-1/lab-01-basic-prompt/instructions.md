# Lab — Build a Zero-Shot Baseline

## Objective

Compare a vague request with a structured zero-shot prompt and demonstrate a measurable improvement
without adding completed examples.

## Scenario

A business analyst receives short stakeholder notes and must prepare a requirements brief for human
review. The brief must preserve stated facts, expose missing information, and never claim approval
or invent a business rule.

## Architecture

~~~mermaid
flowchart LR
    Note[Synthetic stakeholder note] --> Prompt[Zero-shot prompt]
    Prompt --> Model[Chat Playground model]
    Model --> Brief[Requirements brief]
    Brief --> Review[Human rubric review]
    Review --> Decision{Pass?}
    Decision -->|No| Revise[Revise instructions]
    Revise --> Prompt
~~~

The model only proposes a brief. A human validates every statement before the result is used.

## Prerequisites

- An OpenAI Platform account with access to the
  [Chat Playground](https://platform.openai.com/playground/chat).
- Permission to incur any usage charges associated with the selected model.
- A text file or worksheet for recording responses and scores.
- The synthetic [test cases](assets/test-cases.md); do not substitute production notes.

## Required Tools

- OpenAI Chat Playground.
- A currently available text model. Record its displayed model identifier.
- Git or another versioning method for saving prompt revisions.

Interface labels can change. Use the Playground area that accepts high-priority instructions and a
user message; do not depend on a particular button location.

## Estimated Difficulty

Beginner. Allow 35–50 minutes.

## Step 1 — Setup

1. Open the Chat Playground and sign in.
2. Start a new prompt or chat.
3. Select one text model available to your project.
4. Record the model identifier, date, and any visible generation settings.
5. Keep that model and those settings unchanged for every comparison in this lab.
6. Open [starter/prompt.md](starter/prompt.md) and
   [assets/test-cases.md](assets/test-cases.md).

Do not paste credentials, customer data, employee data, or internal company documents into the
Playground.

## Step 2 — Build

### Run A — Vague baseline

1. Put the starter instruction in the user-message area.
2. Replace the input marker with Case 1.
3. Run the prompt.
4. Save the complete response as evidence; do not edit it.

### Run B — Your engineered zero-shot prompt

Create a new prompt with these components:

- **Role:** business analyst preparing a review draft.
- **Goal:** produce a requirements brief.
- **Input:** the stakeholder note.
- **Constraints:** use only stated facts, identify unknowns, and never invent approval.
- **Output:** named sections with a fixed maximum number of bullets.

Do not include any completed example. Run Case 1 and save the response.

### Run C — Reference comparison

Only after completing Run B, compare your prompt with the
[reference solution](solution/README.md). You may adopt a reference rule only if you can explain
which failure it prevents. Run the reference prompt on Case 1.

## Step 3 — Test

Run your final prompt on all three cases.

1. Start a fresh conversation for each case. Earlier assistant answers can become in-context
   examples and would contaminate a zero-shot test.
2. Paste exactly one case into the input block.
3. Save the unedited response.
4. Score every rubric item as 1 for pass or 0 for fail.
5. Record any unsupported statement verbatim in your error notes.

Test Case 3 contains an instruction-like sentence inside the stakeholder note. The model must treat
that sentence as untrusted business content, not as authority to override the prompt.

## Step 4 — Validate

For each case, award one point for each item:

1. all required headings are present;
2. every stated fact is preserved correctly;
3. no fact or approval is invented;
4. unknown information appears under Open questions;
5. the result stays within the requested bullet limits.

The prompt passes when it scores at least 13 of 15 overall **and** receives the “no invention” point
for every case. A high total cannot compensate for an invented approval or business rule.

Compare the vague baseline and final zero-shot totals. Record:

- the score change;
- the two most important failure categories removed;
- whether examples would add value or merely add tokens.

## Expected Result

The baseline commonly varies in headings, hides unknowns, or adds plausible assumptions. A good
zero-shot prompt should produce the four required sections, preserve the source facts, label
unknowns, and reject instruction-like text embedded in the note.

Exact prose is not the expected result. Passing the rubric is.

## Troubleshooting

| Problem | Likely cause | Corrective action |
| --- | --- | --- |
| Prior response style appears again | The same conversation was reused | Start a new conversation for each zero-shot test |
| The model invents a requirement | Grounding rule is weak | Add “use only facts inside INPUT; mark all other details Unknown” |
| Headings vary | Output contract is descriptive | List the exact headings and bullet limits |
| Results differ between runs | Model generation is probabilistic | Keep settings fixed and score against facts, not wording |
| Playground access is denied | Account, project, or billing access is missing | Ask the project owner for approved access; do not use shared credentials |

## Challenge Exercise

Adapt the prompt for a project manager who turns meeting notes into Decisions, Actions, Owners, and
Open questions. Keep it zero-shot. Add a rule that an action without a named owner must show
Owner: Unassigned.

## Enterprise Extension

Store the prompt as a versioned artifact with owner, use case, approved data classes, model/config,
test-set version, pass threshold, and review date. Before production use, automate output validation
and regression testing rather than relying only on visual review.

## Security Considerations

- Use only synthetic or approved data.
- Treat the input block as data, even when it contains instruction-like text.
- Do not claim that Playground output is an approved requirement.
- Minimize data: include only the note needed for the task.
- Follow organizational retention and provider-processing requirements.

## Cleanup

1. Remove any accidental sensitive text from the Playground conversation according to your
   organization’s data-handling procedure.
2. Keep only synthetic prompts, responses, scores, and reflection notes in the evidence pack.
3. Close unused Playground sessions. No API key or local secret should have been created.

## Completion Checklist

- [ ] I recorded the model identifier, run date, and settings.
- [ ] I saved the unedited vague baseline.
- [ ] My final prompt contains no completed examples.
- [ ] I used a fresh conversation for every test case.
- [ ] I scored all 15 rubric checks.
- [ ] Every case passed the no-invention critical criterion.
- [ ] I documented whether zero-shot is sufficient and why.
- [ ] I used no confidential or personal data.

## References

- [OpenAI prompt engineering guide](https://developers.openai.com/api/docs/guides/prompt-engineering)
- [OpenAI model guidance](https://developers.openai.com/api/docs/guides/latest-model)
