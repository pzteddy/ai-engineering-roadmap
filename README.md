# AI Engineering Roadmap

From effective AI use to accountable enterprise AI product ownership.

This repository is a reusable knowledge base and hands-on learning platform for people who need to
move beyond one-off AI demonstrations. It teaches how to improve AI answers, connect models to real
work, engineer measurable production systems, and take responsibility for business outcomes.

> **Repository status:** Phase 1 is the foundation only. The repository structure, learning
> contracts, contribution rules, and roadmap are defined. Detailed lessons and executable labs are
> intentionally delivered in later phases.

## The maturity journey

```text
Level 1 — USE AI
Prompt & Context Engineering
ANSWER
   ↓
Level 2 — BUILD WITH AI
Tools & Automation
ACTION
   ↓
Level 3 — ENGINEER AI
Evaluation, Reliability & Scale
SYSTEM
   ↓
Level 4 — OWN AI
Governance & Responsibility
PRODUCT
   ↓
Enterprise AI Engineer / Solution Owner
```

| Level | Topic | Main goal | Primary output |
| --- | --- | --- | --- |
| 1 | Prompt & Context Engineering | Control AI behavior and improve answer quality | **Answer** |
| 2 | Tools & Automation | Let AI perform bounded work through controlled capabilities | **Action** |
| 3 | Evaluation, Reliability & Scale | Prove the system works and continues to work | **System** |
| 4 | Ownership & Responsibility | Operate AI safely with accountable business ownership | **Product** |

Maturity is not only more capability. Each level adds stronger measurement, control, security, and
accountability.

## Why this repository exists

Modern AI engineering is less about training a model from scratch and more about building a useful,
reliable system around a model. That system includes business requirements, prompts, context,
retrieval, tools, workflow orchestration, deterministic controls, evaluation, observability, and an
accountable owner.

The repository follows four principles:

1. Start with the business problem, not the model.
2. Use the smallest relevant, authoritative, current, sufficient, and authorized context.
3. Keep reasoning separate from authority: AI may propose; controlled systems decide what may execute.
4. Treat quality, security, reliability, cost, and ownership as release requirements.

## Who this repository is for

- Software, integration, RPA, data, and AI engineers.
- Solution and enterprise architects.
- Business analysts, project managers, and product owners.
- Technical consultants and enterprise IT teams.
- Teams designing self-study, workshops, enablement programs, or internal knowledge bases.

The material uses plain language before implementation detail and separates durable engineering
concepts from vendor-specific procedures.

## Learning objectives

After completing the full roadmap, a learner should be able to:

- turn vague requests into structured, reusable, testable AI tasks;
- select governed context and explain why each source is relevant and authorized;
- define tool contracts and connect AI to APIs, databases, RPA, and workflow engines safely;
- choose deterministic workflows over agents when autonomy does not create measured value;
- define acceptance criteria, evaluation datasets, regression gates, and production metrics;
- design for failures across prompts, retrieval, models, tools, and business systems;
- apply least privilege, human approval, auditability, and incident controls according to risk;
- communicate architecture, limitations, cost, and production ownership to enterprise stakeholders.

## Prerequisites

No model-training background is required. Learners should be comfortable with basic computer use,
reading structured data such as JSON, and following command-line instructions. Python, Git, HTTP,
SQL, and cloud concepts become increasingly useful at Levels 2 and 3; the getting-started material
will define the required baseline before those labs are implemented.

## Repository navigation

| Area | Purpose |
| --- | --- |
| [Getting Started](docs/00_Getting_Started/README.md) | Environment, prerequisites, Git workflow, and learning-path orientation. |
| [Level 1 — Prompt & Context](docs/01_Prompt_Context_Engineering/README.md) | Structured instructions, governed context, output contracts, verification, and reuse. |
| [Level 2 — Tools & Automation](docs/02_AI_Tools_Automation/README.md) | Tool calling, APIs, MCP, data access, RPA, workflows, and execution controls. |
| [Level 3 — Evaluation & Scale](docs/03_Evaluation_Reliability_Scale/README.md) | Evaluation datasets, regression testing, observability, reliability, cost, and scale. |
| [Level 4 — Ownership & Responsibility](docs/04_Ownership_Responsibility/README.md) | Governance, security, risk, approvals, audit, incidents, and accountable ownership. |
| [Agentic AI](docs/05_Agentic_AI/README.md) | Agent anatomy, deterministic versus agentic workflows, guardrails, and observability. |
| [Enterprise Architecture](docs/06_Enterprise_Architecture/README.md) | Reusable reference patterns and design-review expectations. |
| [Labs](labs/README.md) | Executable practice organized by maturity level. |
| [Examples](examples/README.md) | Focused prompts, code, API, RAG, MCP, and agent examples. |
| [Architectures](architectures/README.md) | Cross-cutting architecture patterns and decision records. |
| [Templates](templates/README.md) | Reusable project, prompt, risk, evaluation, production, and incident artifacts. |
| [Datasets](datasets/README.md) | Safe sample and evaluation-data conventions. |
| [Scripts](scripts/README.md) | Reproducible setup, test, and evaluation automation. |
| [Assets](assets/README.md) | Source-controlled diagrams, screenshots, and supporting media. |

The [delivery roadmap](ROADMAP.md) contains maturity requirements, recommended evidence, the
eight-week learning sequence, and repository implementation phases.

## Hands-on lab navigation

Every maturity level culminates in applied evidence:

| Level | Lab track | Outcome |
| --- | --- | --- |
| 1 | [Prompt and context labs](labs/level-1/README.md) | A versioned AI assistant with structured output and repeatable quality checks. |
| 2 | [Tools and automation labs](labs/level-2/README.md) | A tool-using workflow with explicit authorization and approval boundaries. |
| 3 | [Evaluation and reliability labs](labs/level-3/README.md) | An evaluated prototype with regression gates, telemetry, and cost/performance evidence. |
| 4 | [Ownership and security labs](labs/level-4/README.md) | A governed production-readiness package with risk, audit, and incident controls. |

Labs are not considered complete when they only display a successful demo. Each lab must provide
setup, build, test, validation, expected results, troubleshooting, security considerations, cleanup,
and a completion checklist.

## Suggested learning sequence

The default path is an eight-week progression with one mini-project at every level:

| Week | Focus | Evidence |
| --- | --- | --- |
| 1 | AI and LLM fundamentals | Capability and limitation assessment |
| 2 | Prompt engineering | Structured, versioned prompt pattern |
| 3 | Context engineering and RAG | Governed context and retrieval design |
| 4 | APIs, tools, and function calling | Validated tool contract |
| 5 | Automation, agents, and MCP | Controlled tool-using workflow |
| 6 | Evaluation, testing, and observability | Golden dataset and regression report |
| 7 | Production architecture, security, and scaling | Production-readiness review |
| 8 | Governance, risk, and product ownership | Governed enterprise AI product proposal |

Teams may change the pace, but should preserve the dependency order and evidence gates.

## Technology stack

The roadmap is concept-first and provider-neutral. Examples may use:

- Python, JavaScript, JSON, Git, GitHub, REST APIs, and SQL;
- model APIs, retrieval systems, vector databases, and Model Context Protocol (MCP);
- workflow and RPA platforms such as n8n and UiPath;
- Azure AI services and Azure AI Document Intelligence;
- testing, evaluation, tracing, monitoring, and cost-analysis tools.

Vendor-specific implementations must remain separate from general concepts, identify version and
access assumptions, and provide a portable explanation of the underlying pattern.

## Evidence standard

A completed artifact should be reproducible and reviewable by someone other than its author. Where
applicable, it includes:

- a business problem, success criteria, non-goals, and named owner;
- documented setup from a clean checkout and safe configuration handling;
- versioned prompts, models, context sources, retrieval settings, and tool definitions;
- deterministic tests plus AI-specific evaluation cases and release thresholds;
- quality, reliability, latency, cost, safety, and business-outcome measurements;
- failure analysis, fallback behavior, escalation paths, and a runbook;
- least-privilege permissions, data handling rules, audit needs, and risk classification;
- known limitations and the evidence that would trigger redesign.

## Security baseline

Never commit credentials, access tokens, production customer data, confidential documents, or
unredacted sensitive logs. Use [.env.example](.env.example) only as a variable-name contract; keep
real values in environment variables or an approved secret manager such as Azure Key Vault,
GitHub Secrets, Managed Identity, or Workload Identity.

Autonomy must decrease as consequence increases. Payment, deletion, external communication, access
changes, and other material actions require stronger deterministic authorization, human approval,
and audit controls than read-only search or recommendation tasks.

## Contributing

Read [CONTRIBUTING.md](CONTRIBUTING.md) before proposing content or code. Contributions must use
relative links, conventional commits, the repository content standard, and the security rules.
Executable examples and labs must include validation and must not depend on undocumented manual
steps.

## Disclaimer

This repository is educational engineering guidance. It does not replace organizational security,
privacy, legal, compliance, accessibility, safety, or model-risk review. High-impact applications
require qualified domain owners and controls appropriate to the affected people, data, and business
process.
