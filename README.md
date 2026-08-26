# AI Engineering Roadmap

A practical, systems-oriented path from software foundations to reliable AI products.
This repository is designed as a durable knowledge base: concepts are tied to implementation,
implementation is tied to evaluation, and every major stage ends with evidence that can be
reviewed or demonstrated.

> **Repository status:** Phase 1 establishes the information architecture, learning contract,
> and delivery roadmap. Curriculum modules and project implementations belong to later phases
> and are intentionally outside this foundation commit.

## Why this repository exists

AI engineering sits at the intersection of software engineering, data, machine learning, and
operations. A list of model tutorials is not enough. An effective roadmap must explain what to
learn, in what order, why each capability matters, and what observable result proves the skill.

This repository organizes that work around four questions:

1. **Can you explain it?** State the mechanism, assumptions, and trade-offs in plain language.
2. **Can you build it?** Implement a working system rather than only reproducing a notebook.
3. **Can you evaluate it?** Define baselines and measure quality, cost, latency, and failure modes.
4. **Can you operate it?** Test, deploy, observe, secure, and improve the system under realistic constraints.

## Intended audience

The roadmap is for software engineers moving into AI, data or ML practitioners strengthening
production skills, and self-directed learners who want a coherent route through a fast-moving
field. It assumes comfort using a computer and reading basic code, but it does not assume prior
professional machine-learning experience.

The sequence is cumulative. Experienced readers can use the exit criteria in
[ROADMAP.md](ROADMAP.md) to test out of familiar phases instead of repeating them.

## Learning model

Each curriculum module added after the foundation phase should follow the same learning loop:

1. **Frame** — identify the user problem, system boundary, and success measures.
2. **Learn** — understand the minimum theory needed to make sound engineering decisions.
3. **Build** — produce a reproducible implementation with explicit assumptions.
4. **Measure** — compare against a baseline and investigate failure cases.
5. **Harden** — add tests, observability, security controls, and operational documentation.
6. **Reflect** — record decisions, limitations, and the next experiment.

Progress is based on demonstrated capability, not time spent. Reading is an input; working,
evaluated artifacts are the evidence.

## Repository map

The numbered directories define the primary dependency order. Their index files are curriculum
contracts: they establish scope and completion evidence without pretending that later-phase
lesson content already exists.

| Path | Responsibility |
| --- | --- |
| [00-orientation](00-orientation/README.md) | Set goals, establish a baseline, and create a reproducible working environment. |
| [01-engineering-foundations](01-engineering-foundations/README.md) | Build the Python, Git, shell, API, testing, and database habits required by every later phase. |
| [02-data-and-ml](02-data-and-ml/README.md) | Develop data quality, experimentation, classical ML, and evaluation judgment. |
| [03-deep-learning](03-deep-learning/README.md) | Learn neural-network training, representation learning, and transformer fundamentals. |
| [04-llm-engineering](04-llm-engineering/README.md) | Engineer model integrations, retrieval systems, tools, agents, and LLM evaluations. |
| [05-production-ai](05-production-ai/README.md) | Deploy, observe, secure, scale, and economically operate AI workloads. |
| [06-ai-systems-design](06-ai-systems-design/README.md) | Make architecture decisions across quality, latency, reliability, safety, and cost. |
| [projects](projects/README.md) | Integrate capabilities through progressively less-scaffolded portfolio projects. |
| [resources](resources/README.md) | Curate durable primary sources and record why each source earns a place. |
| [ROADMAP.md](ROADMAP.md) | Define delivery phases, dependencies, exit criteria, and repository-level milestones. |

## Recommended paths

### Full path

Follow the numbered directories in order, completing the corresponding project gate before
advancing. This path is appropriate when one or more foundations are new or when previous
experience is mostly notebook-based.

### Experienced engineer path

Start with the orientation assessment, then use each phase's exit criteria as a challenge. Keep
the evidence when you pass; study only the gaps when you do not. Do not skip data evaluation or
production operations simply because application development is familiar.

### ML practitioner path

Validate the engineering foundation first, move quickly through familiar modeling material, and
spend the saved time on APIs, testing, deployment, observability, system design, and incident
analysis.

## Evidence standard

A completed learning artifact should be understandable and reproducible by someone other than
its author. As applicable, it includes:

- a precise problem statement and declared non-goals;
- setup and execution instructions from a clean environment;
- versioned code, configuration, and data assumptions;
- automated tests for deterministic behavior;
- evaluation data, a baseline, chosen metrics, and failure analysis;
- security, privacy, cost, and operational considerations;
- an architecture or decision record for non-obvious trade-offs;
- known limitations and a concrete improvement hypothesis.

A successful demo without repeatable evaluation is incomplete. A strong metric without a usable,
operable system is also incomplete.

## Suggested study cadence

Use a cadence that can be sustained for months rather than a short burst that produces fragile
knowledge.

| Weekly capacity | Suggested split |
| --- | --- |
| 5–7 hours | 2 hours concepts, 3 hours implementation, 1–2 hours review and documentation |
| 10–15 hours | 3 hours concepts, 6–9 hours implementation, 1–3 hours evaluation and reflection |
| 20+ hours | Preserve at least half the time for projects, tests, evaluation, and operational work |

At the end of each week, record one capability gained, one unresolved failure mode, and the next
smallest test that would reduce uncertainty.

## Repository quality bar

Content added to this knowledge base should be:

- **Specific:** name tools and techniques only when their role and trade-offs are explained.
- **Evidence-led:** prefer primary documentation, papers, standards, and reproducible measurements.
- **Tool-aware, not tool-dependent:** teach durable concepts while acknowledging current implementations.
- **Production-minded:** include testing, observability, security, accessibility, privacy, and cost where relevant.
- **Navigable:** preserve the numbered learning sequence and use relative links for repository content.
- **Maintainable:** date time-sensitive claims and avoid copying material that can be linked to its authoritative source.

## Scope boundaries

This is an engineering roadmap, not a promise that every learner will need every model architecture
or vendor platform. It prioritizes transferable judgment and the ability to deliver dependable AI
systems. It does not replace formal safety review, domain expertise, legal advice, or the controls
required for regulated and high-impact applications.

## Start here

Read the [delivery roadmap](ROADMAP.md), then begin with the
[orientation contract](00-orientation/README.md). Before moving to a later phase, compare your
evidence with that phase's exit criteria instead of relying on perceived familiarity.
