# Hands-on Labs

Labs convert the roadmap into reviewable engineering evidence. The four tracks follow the maturity
journey: improve answers, enable controlled action, prove system reliability, and own production
outcomes.

## Tracks

| Track | Capability | Required integrated outcome |
| --- | --- | --- |
| [Level 1](level-1/README.md) | Prompt & Context | Versioned AI assistant with structured output and repeatable evaluation |
| [Level 2](level-2/README.md) | Tools & Automation | Bounded tool-using workflow with authorization and approval controls |
| [Level 3](level-3/README.md) | Evaluation & Scale | Evaluated system with regression gate, observability, and cost evidence |
| [Level 4](level-4/README.md) | Ownership & Responsibility | Governed production-readiness package with risk and incident controls |

## Lab directory contract

Every implemented lab must contain:

```text
README.md          # purpose, learning outcomes, support boundary, and navigation
instructions.md    # complete learner workflow
starter/           # safe starting code or configuration
solution/          # reference implementation with no real credentials
assets/            # synthetic inputs and supporting media
```

An `instructions.md` must cover objective, scenario, architecture, prerequisites, required tools,
difficulty, setup, build, test, validation, expected result, troubleshooting, challenge exercise,
enterprise extension, security considerations, cleanup, and completion checklist.

## Executability standard

- Setup must work from a clean checkout using declared versions.
- Inputs must be synthetic or explicitly approved and safe to redistribute.
- External dependencies, accounts, permissions, regions, and potential cost must be declared.
- Expected output must be testable rather than described as “looks good.”
- Success, invalid-input, unavailable-dependency, and unauthorized paths must be exercised.
- Billable resources and local sensitive artifacts must have cleanup instructions.
- Solutions must demonstrate the intended pattern without hiding material manual steps.

## Evidence standard

Each lab produces a concise evidence pack: implementation, test result, evaluation result, decision
or architecture note, security review, limitations, and learner reflection. Later levels accumulate
earlier evidence rather than discarding it.

## Phase status

Phase 1 defines these contracts and tracks. Executable lab directories are implemented in repository
delivery Phase 7; this foundation does not claim they already exist.

[Repository overview](../README.md) · [Maturity roadmap](../ROADMAP.md)
