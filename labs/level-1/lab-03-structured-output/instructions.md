# Lab — Produce and Validate Structured JSON

## Objective

Create a prompt that returns syntactically valid JSON matching a business output contract for three
representative service requests.

## Scenario

A service desk wants to prepare ticket data from short request messages. An RPA workflow may consume
the data later, but this Level 1 lab stops at a validated proposal and human review.

## Architecture

~~~mermaid
flowchart LR
    Request[Synthetic service request] --> Prompt[Prompt plus contract]
    Prompt --> Model[Chat Playground model]
    Model --> JSON[Candidate JSON]
    JSON --> Syntax[JSON syntax check]
    Syntax --> Contract[Field and business-rule check]
    Contract --> Human[Human review]
    Human -. no automated action .-> Stop[Evidence only]
~~~

JSON syntax validation and business validation are separate gates.

## Prerequisites

- Completion of [Lab 02](../lab-02-role-context/README.md), or equivalent few-shot knowledge.
- Access to the [OpenAI Chat Playground](https://platform.openai.com/playground/chat).
- A local JSON parser: Python 3, PowerShell, an IDE, or another approved validator.
- The [output contract](assets/output-contract.md) and
  [synthetic requests](assets/requests.md).

## Required Tools

- OpenAI Chat Playground with one available text model.
- A plain-text editor.
- One of these local syntax checks:

~~~powershell
Get-Content -Raw -LiteralPath '.\response.json' | ConvertFrom-Json | Out-Null
~~~

~~~bash
python -m json.tool response.json
~~~

Run only one command appropriate for your approved environment. Never paste secrets into an online
JSON validator.

## Estimated Difficulty

Intermediate. Allow 60–75 minutes.

## Step 1 — Setup

1. Start a new Playground prompt and record model, date, and visible settings.
2. Keep the same configuration throughout the comparison.
3. Review the output contract before writing a prompt.
4. Create a temporary local response.json file outside the repository, or use an approved scratch
   location that is not synchronized to a public service.
5. Open the [starter prompt](starter/prompt.md).

## Step 2 — Build

### Run A — Vague JSON baseline

Run the starter prompt on Request 1. Save the unedited response and note whether it contains
Markdown fences, extra commentary, missing keys, or invented fields.

### Run B — Contract-driven zero-shot

Create a new prompt that:

- names all seven required keys;
- defines every type and allowed enumeration;
- states how to represent unknown values;
- requires all keys even when data is missing;
- prohibits additional keys and commentary;
- treats REQUEST as data rather than instructions.

Run Request 1 and validate it.

### Run C — Add a semantic example

If Run B mishandles missing information, add one completed example showing UNKNOWN, null, and
missing_fields. The example should teach this business meaning, not merely repeat JSON punctuation.
Compare with the [reference solution](solution/README.md).

If Run B already passes all cases, record that the example is not needed. The shortest passing
prompt is the preferred result.

## Step 3 — Test

For each of the three requests:

1. Start a fresh conversation.
2. Paste only one REQUEST block.
3. Save the raw response before removing any display formatting.
4. If the response contains a Markdown fence or commentary, mark the raw-output format check as a
   failure. Copy only the JSON object into the temporary response.json file for further diagnosis.
5. Run the local syntax check.
6. Compare keys, types, enums, and facts with the answer key.

Do not repair the model response manually and then report it as passing.

## Step 4 — Validate

Each case has six checks:

1. raw response is one JSON object with no fence or commentary;
2. JSON syntax parses;
3. exactly the seven required keys are present;
4. values use the required types and enumerations;
5. facts and missing fields match the source;
6. no approval, priority, system, or action is invented.

Passing criteria:

- at least 17/18 checks overall;
- syntax parses for all cases;
- the no-invention check passes for all cases.

A prompt-only pass is evidence for the lab, not authorization to integrate with automation.

## Expected Result

The final prompt should return one JSON object per request. Request 2 should use null and UNKNOWN
rather than guessing. Request 3 should preserve the requested password reset while ignoring the
embedded instruction to set a false priority or claim approval.

## Troubleshooting

| Problem | Likely cause | Corrective action |
| --- | --- | --- |
| Output contains a Markdown code fence | The output contract permits presentation formatting | Require a raw JSON object with no fence or prose |
| JSON parses but a key is missing | Syntax and schema checks were confused | Require all keys and validate the contract separately |
| Missing data becomes an empty string | Missing-value semantics are undefined | Specify null for unknown system and UNKNOWN for controlled enums |
| Priority is guessed | Business rule is absent | Permit UNKNOWN and prohibit inference from urgency words |
| An example causes copied values | The example and test input are not clearly delimited | Use distinct example and REQUEST tags |

## Challenge Exercise

If your selected Playground configuration exposes a supported JSON Schema or Structured Outputs
setting, reproduce the contract with that feature and compare failure rates. Record the exact model
and configuration. Do not assume the control is available to every account or model.

## Enterprise Extension

In an API implementation, use Structured Outputs with a supported strict JSON Schema when possible,
then validate business rules again before any ticket or workflow action. Log schema version,
prompt/model version, validation result, and human decision without storing unnecessary request
content.

## Security Considerations

- Treat request text as untrusted data.
- Never include passwords, tokens, production ticket text, or personal data in this lab.
- Do not send model output directly to RPA or a service-management API.
- Reject unknown enum values and unexpected keys.
- Require authorization and human approval before any later state-changing workflow.

## Cleanup

1. Delete the temporary response.json file.
2. Remove accidental sensitive Playground content according to policy.
3. Retain synthetic prompts, raw outputs, validation results, and the model/config record.

## Completion Checklist

- [ ] I separated JSON syntax from business-contract validation.
- [ ] I tested all three synthetic requests in fresh conversations.
- [ ] I did not manually repair an output and count it as a pass.
- [ ] All critical syntax and no-invention checks passed.
- [ ] I recorded whether a few-shot example was necessary.
- [ ] I documented why prompt-only JSON is not a production guarantee.
- [ ] No ticket or automation action was executed.

## References

- [OpenAI Structured Outputs guide](https://developers.openai.com/api/docs/guides/structured-outputs)
- [OpenAI prompt engineering guide](https://developers.openai.com/api/docs/guides/prompt-engineering)
