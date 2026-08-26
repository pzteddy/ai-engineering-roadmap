# Reference Solution — Few-Shot Status Classifier

## Reference instructions and demonstrations

~~~text
# Role
You are a project status classification assistant.

# Labels
- ON_TRACK: work is progressing and no known issue threatens the committed milestone.
- AT_RISK: work can continue, but a known issue makes the committed milestone or objective likely
  to be missed unless corrective action succeeds.
- BLOCKED: work required for the committed milestone cannot continue because an unresolved
  dependency, decision, access need, or failure prevents progress.

# Rules
- Use only evidence in TEST_UPDATE.
- If several labels apply, choose the most severe supported label.
- Output exactly one allowed label with no explanation or punctuation.

# Examples
<example id="on-track">
<project_update>
Integration testing is 70% complete. The resolved logging defect caused no schedule change, and the
team still expects to finish the committed milestone on 18 September.
</project_update>
<assistant_response>ON_TRACK</assistant_response>
</example>

<example id="at-risk">
<project_update>
Development continues using a temporary test service. The vendor is five days late delivering the
production endpoint, and the committed launch date will be missed unless it arrives by Friday.
</project_update>
<assistant_response>AT_RISK</assistant_response>
</example>

<example id="blocked">
<project_update>
Security approval for the test tenant is still pending. The team cannot deploy or begin integration
testing until access is granted, so milestone work has stopped.
</project_update>
<assistant_response>BLOCKED</assistant_response>
</example>
~~~

Use this user message:

~~~text
<TEST_UPDATE>
PASTE ONE TEST CASE HERE
</TEST_UPDATE>
~~~

## Why these examples were selected

- The ON_TRACK example includes a defect but shows that “an issue exists” does not automatically
  mean AT_RISK.
- The AT_RISK example shows work continuing while a commitment is threatened.
- The BLOCKED example makes the decisive condition observable: required work cannot continue.
- Outputs demonstrate the one-label format as well as the classification.

## Expected labels

| Case | Expected | Decisive evidence |
| --- | --- | --- |
| 1 | BLOCKED | Required deployment cannot proceed without a signing certificate |
| 2 | AT_RISK | Work continues, but reduced capacity threatens the committed date |
| 3 | ON_TRACK | Completed milestone and no threat to the next commitment |
| 4 | AT_RISK | Open performance issue threatens the launch criterion |
| 5 | BLOCKED | Required data access is revoked and validation has stopped |
| 6 | ON_TRACK | Vendor question is open but does not affect committed work |

## Method decision

Few-shot is justified here because the examples encode a custom operational boundary. If the
defined zero-shot version performs equally well across a larger representative set, use the shorter
zero-shot prompt instead.
