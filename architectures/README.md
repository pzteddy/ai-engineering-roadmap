# Architecture Library

The architecture library will hold reusable patterns and decision records that cut across the
ordered curriculum. Its purpose is to make system boundaries and trade-offs reviewable—not to
collect attractive diagrams without operational meaning.

## Planned patterns

| Pattern | Core decision |
| --- | --- |
| AI-assisted application | Where human decision responsibility remains after an AI response |
| Retrieval-augmented generation | How authoritative context is selected, authorized, and evaluated |
| Document AI | How extraction is validated before business rules or ERP updates |
| Enterprise agent | How reasoning, policy, tools, truth, reconciliation, and audit are separated |
| Human approval | Which actions require approval and what makes approval effective |
| Hybrid automation | When to combine APIs, workflow orchestration, and RPA for legacy systems |
| Production AI platform | How serving, evaluation, observability, security, and ownership interact |

## Architecture document contract

Every implemented architecture must include:

- the business problem, users, workload, and measurable outcome;
- components and end-to-end data/action flow;
- trust boundaries, identities, permissions, data classification, and secret handling;
- system-of-record, transaction, idempotency, and reconciliation behavior;
- failures, timeouts, retries, fallback, escalation, recovery, and kill-switch behavior;
- logs, metrics, traces, evaluation signals, business KPIs, and cost attribution;
- advantages, limitations, alternatives, assumptions, and evolution triggers;
- named business, product, technical, security, and operational ownership.

Use Mermaid for maintainable diagrams when practical. Any external image must have documented source
and reuse rights under [assets](../assets/README.md).

Related: [Enterprise Architecture curriculum](../docs/06_Enterprise_Architecture/README.md) ·
[Maturity roadmap](../ROADMAP.md)
