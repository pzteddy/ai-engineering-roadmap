# Prompt Strategy Decision Record

Copy one row per scenario into your evidence notes.

## Selection matrix

| Scenario | Task | Needed current/private facts? | Custom pattern or boundary? | Consequence | Starting method | Why | External controls |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A |  |  |  |  |  |  |  |
| B |  |  |  |  |  |  |  |
| C |  |  |  |  |  |  |  |
| D |  |  |  |  |  |  |  |
| E |  |  |  |  |  |  |  |
| F |  |  |  |  |  |  |  |
| G |  |  |  |  |  |  |  |
| H |  |  |  |  |  |  |  |

## Version log

| Version | Strategy | Single logical change | Model/config | Tests passed | Failures | Decision |
| --- | --- | --- | --- | ---: | --- | --- |
| v0 | Baseline | Initial request |  |  |  |  |
| v1 |  |  |  |  |  |  |
| v2 |  |  |  |  |  |  |

## Failure taxonomy

- **Instruction:** task, constraints, or success criteria are unclear.
- **Example:** a custom boundary or pattern is not demonstrated well.
- **Context:** required facts are absent, stale, irrelevant, unauthorized, or too large.
- **Format:** response does not match the usable output contract.
- **Grounding:** claims cannot be traced to supplied evidence.
- **Safety:** untrusted text overrides rules or sensitive data is exposed.
- **Missing control:** the task needs authorization, approval, validation, or audit outside the
  prompt.

## Final recommendation

Record the smallest passing prompt, why it passes, known limitations, human owner, and evidence that
would trigger another redesign.
