# Knowledge Areas

The `docs` tree is the ordered curriculum for the AI engineering maturity journey. Phase 1 provides
domain contracts only: each index defines scope, outcomes, safety boundaries, and the evidence that
future lessons must produce. Detailed topic pages are implemented incrementally in later phases.

## Learning sequence

| Order | Knowledge area | Capability transition |
| --- | --- | --- |
| 0 | [Getting Started](00_Getting_Started/README.md) | Establish a safe, reproducible learning environment. |
| 1 | [Prompt & Context Engineering](01_Prompt_Context_Engineering/README.md) | Vague request → controlled, testable answer |
| 2 | [AI Tools & Automation](02_AI_Tools_Automation/README.md) | Answer → bounded business action |
| 3 | [Evaluation, Reliability & Scale](03_Evaluation_Reliability_Scale/README.md) | Working demo → measurable production system |
| 4 | [Ownership & Responsibility](04_Ownership_Responsibility/README.md) | Reliable system → governed enterprise product |
| 5 | [Agentic AI](05_Agentic_AI/README.md) | Fixed workflow → justified, bounded adaptive behavior |
| 6 | [Enterprise Architecture](06_Enterprise_Architecture/README.md) | Individual techniques → coherent enterprise design |

Agentic AI and enterprise architecture are cross-cutting areas. They depend on the controls taught
across Levels 2–4 and should not be treated as shortcuts around evaluation, authorization, or
ownership.

## Document contract

When a detailed knowledge page is implemented, it should cover the sections defined in
[CONTRIBUTING.md](../CONTRIBUTING.md): overview, importance, learning objectives, concepts,
architecture, operation, steps, examples, mistakes, troubleshooting, security, best practices,
takeaways, exercise, checklist, and authoritative references.

Documents must:

- explain the concept before prescribing tools;
- state prototype and production differences;
- connect each technique to business requirements and failure modes;
- identify trust, authorization, data, and system-of-record boundaries;
- define reviewable completion evidence rather than subjective familiarity;
- use relative links and preserve vendor-neutral guidance.

## Completion model

A domain is implemented only when its planned lessons, examples, exercises, validations, security
guidance, and navigation work together. An index alone establishes scope but does not mark later-phase
curriculum content complete.

[Repository overview](../README.md) · [Maturity roadmap](../ROADMAP.md)
