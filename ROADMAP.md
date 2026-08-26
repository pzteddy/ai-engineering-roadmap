# AI Engineering Roadmap Delivery Plan

This document is both a curriculum sequence and a repository delivery plan. It makes dependencies
explicit, defines evidence-based exit criteria, and prevents later topics from being added as an
unstructured collection of links.

## How to read this roadmap

Each phase has two kinds of outcomes:

- **Learner outcomes** describe capabilities a reader should demonstrate.
- **Repository outcomes** describe the material and quality controls that must exist before that
  phase can be considered implemented.

Status applies to repository delivery, not to an individual learner.

| Status | Meaning |
| --- | --- |
| **Complete** | Scope, structure, and exit criteria are implemented and validated. |
| **Planned** | Sequenced and bounded here, but implementation is intentionally deferred. |

## Phase summary

| Phase | Focus | Repository status | Primary evidence |
| --- | --- | --- | --- |
| 1 | Knowledge repository foundation | **Complete** | Navigable structure, content contracts, validated links, and Git history |
| 2 | Orientation and engineering foundations | **Planned** | Tested service, reproducible environment, and engineering baseline |
| 3 | Data and applied machine learning | **Planned** | Reproducible experiment with leakage-safe evaluation |
| 4 | Deep learning foundations | **Planned** | Instrumented training pipeline and model analysis |
| 5 | LLM application engineering | **Planned** | Evaluated retrieval/tool-using application with explicit failure taxonomy |
| 6 | Production AI and operations | **Planned** | Deployed, observable, secured service with rollback and cost controls |
| 7 | AI systems design | **Planned** | Defensible architecture and capacity/reliability analysis |
| 8 | Integrated portfolio | **Planned** | End-to-end capstone with reviewable engineering evidence |

## Phase 1 — Knowledge repository foundation

**Objective:** establish a repository that can grow without losing sequence, quality, or navigability.

### Delivered

- A clear mission, audience, learning model, evidence standard, and scope in the root
  [README](README.md).
- A dependency-ordered directory structure covering the AI engineering lifecycle.
- Curriculum contracts for every domain, including outcomes, evidence, and boundaries.
- This phased delivery plan with measurable exit criteria for future work.
- A Git repository on `main` with a focused foundation commit.

### Exit criteria

- Every tracked directory has an explanatory index; no empty directories or marker-only files are used.
- Every relative Markdown link resolves to a repository file or a valid in-page heading.
- Future phases are described precisely enough to guide implementation without presenting plans as completed content.
- The working tree is inspected before the foundation commit.

No lessons, code labs, datasets, or capstone implementations are part of Phase 1.

## Phase 2 — Orientation and engineering foundations

**Domains:** [orientation](00-orientation/README.md) and
[engineering foundations](01-engineering-foundations/README.md)

**Objective:** create the software delivery baseline required for trustworthy AI work.

### Learner outcomes

- Translate a product problem into testable requirements and measurable acceptance criteria.
- Use Python packaging, type hints, exceptions, logging, and configuration deliberately.
- Work confidently with Git, shell tools, environments, HTTP, APIs, SQL, and containers.
- Write unit, integration, and contract tests and diagnose failures from evidence.
- Expose a small capability through a documented service boundary.

### Repository outcomes

- A diagnostic entry assessment with routing guidance based on observed gaps.
- Short concept notes paired with executable exercises and expected behavior.
- A reference service that demonstrates packaging, tests, persistence, configuration, and CI.
- Troubleshooting material that teaches diagnosis rather than command copying.

### Exit criteria

From a clean checkout, the learner can build, test, and run a typed Python service backed by a
database; explain its API and failure behavior; and use Git history to review the work. The service
must reject invalid input, log useful context without secrets, and include automated tests at more
than one boundary.

## Phase 3 — Data and applied machine learning

**Domain:** [data and machine learning](02-data-and-ml/README.md)

**Objective:** turn imperfect data into defensible predictions and decisions.

### Learner outcomes

- Profile data and identify missingness, bias, label ambiguity, leakage, and drift risks.
- Establish a simple baseline before increasing model complexity.
- Select splits and metrics that match the decision context and error costs.
- Build reproducible feature and training pipelines rather than stateful notebook sequences.
- Communicate uncertainty, subgroup behavior, limitations, and experiment conclusions.

### Repository outcomes

- Worked examples for tabular data, text features, supervised learning, and unsupervised analysis.
- Evaluation modules covering calibration, thresholding, class imbalance, and error analysis.
- Reproducibility guidance for data lineage, environments, seeds, and experiment records.
- A project gate with a review rubric focused on validity rather than leaderboard performance.

### Exit criteria

The learner can reproduce an experiment from source data, justify the split and metric, compare a
candidate against a baseline, rule out common leakage paths, analyze material errors, and package
inference behind a stable interface.

## Phase 4 — Deep learning foundations

**Domain:** [deep learning](03-deep-learning/README.md)

**Objective:** understand and operate neural training systems well enough to debug and adapt them.

### Learner outcomes

- Explain tensors, gradients, optimization, regularization, batching, and representation learning.
- Implement and inspect a training loop with checkpoints and validation.
- Diagnose underfitting, overfitting, unstable optimization, and data pipeline bottlenecks.
- Use transfer learning and embeddings with an informed view of their limitations.
- Explain attention and transformer components at an implementation-relevant level.

### Repository outcomes

- Framework-backed labs that expose, rather than hide, training mechanics.
- Controlled experiments showing the effects of optimization and regularization choices.
- Compute-aware guidance covering memory, throughput, reproducibility, and checkpointing.
- A model-card-style report template grounded in measured behavior.

### Exit criteria

The learner can train or adapt a neural model, recover the run from a checkpoint, interpret training
and validation signals, investigate a failed run systematically, and report performance and resource
usage against a baseline.

## Phase 5 — LLM application engineering

**Domain:** [LLM engineering](04-llm-engineering/README.md)

**Objective:** build model-powered applications whose behavior is measurable and bounded.

### Learner outcomes

- Choose models and interaction patterns based on quality, latency, context, privacy, and cost.
- Use structured outputs and validation instead of depending on prose conventions.
- Design retrieval pipelines and test each stage independently.
- Add tools and agentic control flow only when they improve a measured task outcome.
- Construct representative evaluation sets and maintain a useful failure taxonomy.
- Defend against prompt injection, unsafe tool use, data exposure, and unbounded execution.

### Repository outcomes

- Modules for model APIs, context management, structured generation, retrieval, tools, and workflows.
- Provider-neutral interfaces with documented vendor-specific examples where useful.
- Offline and online evaluation patterns, including human review and regression gates.
- Security exercises that demonstrate both attacks and layered mitigations.

### Exit criteria

The learner can deliver an LLM application with a versioned evaluation set, baseline comparison,
validated outputs, source-aware retrieval where needed, bounded tools, a documented threat model,
and measured quality, latency, and per-task cost.

## Phase 6 — Production AI and operations

**Domain:** [production AI](05-production-ai/README.md)

**Objective:** operate AI services reliably as models, data, traffic, and dependencies change.

### Learner outcomes

- Package and deploy inference workloads with repeatable configuration and release procedures.
- Define service-level indicators and objectives for user-visible behavior.
- Observe application, retrieval, model, and data quality without collecting unsafe telemetry.
- Use caching, batching, queues, routing, and fallbacks to control performance and cost.
- Detect drift and regressions, manage versions, and execute rollback or recovery.
- Apply secrets management, least privilege, supply-chain controls, and incident response.

### Repository outcomes

- Deployment patterns for synchronous, asynchronous, batch, and streaming workloads.
- Observability examples spanning logs, metrics, traces, evaluations, and cost attribution.
- Release and rollback exercises with failure injection.
- Operational runbooks and a blameless incident-analysis example.

### Exit criteria

The learner can deploy the Phase 5 system, define and measure its service objectives, identify a
regression through telemetry, safely roll back or degrade service, estimate capacity and cost, and
document security and recovery procedures.

## Phase 7 — AI systems design

**Domain:** [AI systems design](06-ai-systems-design/README.md)

**Objective:** make defensible architecture decisions under real product and operational constraints.

### Learner outcomes

- Decompose an AI product into data, model, retrieval, orchestration, serving, and feedback boundaries.
- Quantify latency budgets, capacity, availability, consistency, and cost trade-offs.
- Decide when to buy, adapt, train, cache, route, or remove a model dependency.
- Design for graceful degradation and the failure of external providers.
- Include privacy, safety, abuse prevention, and governance in the architecture rather than after it.

### Repository outcomes

- Case studies with constraints, competing designs, and explicit decisions.
- Capacity-planning and cost-modeling exercises using stated assumptions.
- Architecture review rubrics that test failure handling and operational ownership.
- Decision records that show how an architecture should evolve when assumptions change.

### Exit criteria

Given an ambiguous product scenario, the learner can clarify requirements, propose at least two
credible architectures, quantify the important trade-offs, choose one, describe failure and recovery
behavior, and identify the evidence that could invalidate the decision.

## Phase 8 — Integrated portfolio

**Domain:** [projects](projects/README.md)

**Objective:** combine the roadmap's capabilities in work that can withstand engineering review.

### Learner outcomes

- Own a problem from discovery through operations and retrospective.
- Make trade-offs visible through concise requirements, experiments, and decision records.
- Demonstrate improvement over a baseline using reproducible evaluation.
- Communicate the system to technical and non-technical reviewers.

### Repository outcomes

- Three project tiers: guided, specification-led, and independently scoped capstone.
- Rubrics covering product fit, software quality, evaluation validity, reliability, safety, and communication.
- Review checklists that reward evidence and penalize hidden manual steps.
- Example project briefs that are domain-diverse without prescribing a single vendor stack.

### Exit criteria

The capstone is runnable from documented instructions, tested at meaningful boundaries, evaluated on
representative cases, observable in operation, and accompanied by an architecture explanation,
threat model, cost analysis, runbook, and limitations. A reviewer can trace each major claim to code,
data, or measured evidence.

## Dependency and project gates

The phases are ordered, but projects should appear throughout the path rather than only at the end.

| After phase | Project gate | Principal review question |
| --- | --- | --- |
| 2 | Reliable data-backed API | Can another engineer run, test, and change it safely? |
| 3 | Evaluated predictive service | Is the claimed improvement valid and reproducible? |
| 4 | Instrumented training pipeline | Can the learner diagnose behavior and resource use? |
| 5 | Evaluated LLM application | Are model behavior and failure modes measured and bounded? |
| 6 | Operated AI service | Will the service degrade safely and recover from regressions? |
| 7–8 | Capstone and architecture review | Are the product and system trade-offs defensible end to end? |

## Maintenance policy

AI tooling changes faster than the underlying engineering responsibilities. To keep this roadmap
useful:

- teach stable concepts before vendor-specific procedures;
- cite primary sources and record access dates for time-sensitive claims;
- isolate provider examples behind clear interfaces and label their assumptions;
- review links, dependencies, and version-sensitive instructions as part of every content change;
- require a migration note when a change invalidates a previously documented workflow;
- preserve historical decisions when they explain why the current structure exists.

The root [README](README.md) defines the repository-wide quality bar. Domain indexes may tighten that
bar, but should not silently weaken it.
