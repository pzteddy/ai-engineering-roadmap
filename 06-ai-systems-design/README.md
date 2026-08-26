# AI Systems Design

AI systems design integrates product requirements, data, models, infrastructure, safety, and
operations into an architecture that can be defended with explicit assumptions.

## Scope

- Requirement clarification, non-functional constraints, and success measures.
- Data, training, retrieval, orchestration, serving, and feedback-loop boundaries.
- Latency budgets, throughput, concurrency, availability, consistency, and backpressure.
- Model selection, adaptation, routing, caching, build-versus-buy, and provider resilience.
- Failure isolation, fallbacks, idempotency, recovery objectives, and graceful degradation.
- Privacy, safety, abuse resistance, governance, human oversight, and audit needs.
- Capacity, total cost, organizational ownership, and evolutionary architecture.

## Expected outcomes

A learner can turn an ambiguous AI product request into constraints, alternatives, and a justified
design. They quantify the trade-offs that matter, state what would invalidate the decision, and
describe behavior when a model, data source, provider, or internal component fails.

## Completion evidence

- A requirements brief with workload, quality, reliability, privacy, and cost constraints.
- At least two credible architectures and a decision record selecting between them.
- Back-of-the-envelope capacity, latency, availability, and cost calculations.
- Failure-mode analysis, threat model, degradation policy, and recovery plan.
- An evolution path showing how the design changes at stated scale or quality thresholds.

## Engineering bar

Diagrams without quantified assumptions are incomplete. A strong design connects every important
component to ownership, observability, failure behavior, and a reason it exists.

Previous: [Production AI](../05-production-ai/README.md) ·
Next: [Integrated projects](../projects/README.md) ·
[Repository overview](../README.md)
