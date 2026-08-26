# Getting Started

This area prepares learners and facilitators to use the roadmap safely and reproducibly. It is the
entry gate for all four maturity levels, not an optional preface.

## Outcomes

Before starting Level 1, a learner should be able to:

- explain the `Use → Build → Engineer → Own` maturity model;
- identify a real business workflow and its current pain, owner, users, and constraints;
- use Git to create and review a focused change;
- establish an isolated local environment without committing secrets;
- distinguish synthetic, approved, confidential, and prohibited data;
- record tool versions and repeat a basic setup from documented instructions.

## Planned foundation topics

| Topic | Purpose |
| --- | --- |
| Environment setup | Define supported runtimes, package managers, and verification commands. |
| Required tools | Separate essential tools from optional vendor integrations. |
| Git and GitHub basics | Establish branches, commits, reviews, and safe secret handling. |
| Learning path | Route learners by demonstrated capability and available time. |
| Responsible use baseline | Define data, model, license, security, and high-impact-use boundaries. |

## Environment principles

- Start from a clean checkout and use isolated dependencies.
- Store configuration in environment variables and secret managers, never source files.
- Use [.env.example](../../.env.example) only to discover required variable names.
- Prefer synthetic or explicitly approved datasets for exercises.
- Record versions for runtimes, libraries, model APIs, and external services.
- Provide setup and cleanup for both local artifacts and billable cloud resources.

## Entry assessment

The future assessment should test explanation, implementation, debugging, and design—not just
self-rating. Experienced learners may test out of familiar material by retaining evidence that meets
the corresponding level exit criteria in the root [roadmap](../../ROADMAP.md).

## Completion evidence

- A dated skills baseline with supporting examples and identified gaps.
- A selected enterprise use case with measurable outcome and explicit non-goals.
- A clean environment check that reveals no credential values.
- A Git change with a conventional commit and reviewed status.
- A personal or team learning agreement defining pace, review cadence, and escalation needs.

Next: [Level 1 — Prompt & Context Engineering](../01_Prompt_Context_Engineering/README.md) ·
[Knowledge areas](../README.md)
