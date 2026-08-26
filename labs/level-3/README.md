# Level 3 Labs — Evaluation, Reliability & Scale

The Level 3 track turns the Level 2 workflow into an evaluated and operable system. Success means
meeting declared thresholds under realistic cases and failures, not reproducing one demonstration.

## Planned lab sequence

| Lab | Capability | Verifiable result |
| --- | --- | --- |
| AI evaluation | Translate requirements into metrics | Acceptance criteria trace to evaluated cases |
| Golden dataset | Curate representative evidence | Normal, edge, failure, high-risk, and adversarial coverage |
| Regression test | Gate prompt/model/tool changes | Candidate is accepted or rejected by declared thresholds |
| Observability | Trace the complete workflow | Failure is diagnosed from safe correlated telemetry |
| Cost and performance | Measure production economics | Latency distribution, throughput, and cost per success |

## Integrated mini-project

Harden the Level 2 workflow into an evaluated production prototype. Version all behavior-affecting
components, define a release gate, inject failures, and demonstrate rollback or safe degradation.

## Completion gate

- Requirements, metrics, evaluation cases, thresholds, and production KPIs are traceable.
- A simple baseline is compared with the candidate system.
- The regression suite covers quality, grounding, tool use, safety, latency, and cost as applicable.
- Telemetry can explain a failed transaction without exposing prohibited data.
- Retry, fallback, escalation, rollback, capacity, and cost assumptions are tested or measured.

Previous: [Level 2 labs](../level-2/README.md) · Next: [Level 4 labs](../level-4/README.md)
