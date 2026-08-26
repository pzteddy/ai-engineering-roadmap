# Contributing to the AI Engineering Roadmap

Contributions should make the repository more accurate, executable, secure, or easier to learn from.
Volume is not a goal. A focused guide with working evidence is more valuable than a broad page that
only lists tools.

## Before starting

1. Read the root [README](README.md) and [roadmap](ROADMAP.md).
2. Confirm the change belongs to the current repository delivery phase.
3. Search for existing coverage and preserve useful material instead of creating a parallel taxonomy.
4. Define the learner outcome and the evidence that will demonstrate it.
5. Separate general engineering guidance from vendor-specific implementation details.

## Git workflow

Use `main` as the stable branch. Team repositories may use `develop` for integration and the
following short-lived branch prefixes:

- `feature/` for capabilities or examples;
- `docs/` for learning content and navigation;
- `lab/` for executable labs;
- `fix/` for corrections;
- `refactor/` for non-behavioral organization changes.

Recommended flow:

```text
create branch → make focused change → validate → commit → open pull request → review → merge
```

Use conventional commits. Examples:

```text
docs: add prompt engineering guide
lab: add RAG evaluation exercise
feat: add MCP tool example
fix: correct regression metric calculation
refactor: separate provider adapter from core workflow
```

Do not rewrite shared history or combine unrelated changes in one commit.

## Knowledge-document standard

Detailed learning documents should use the following sections when applicable. A section may be
omitted only when it genuinely does not apply; do not retain empty headings.

```markdown
# Topic Name

## Overview
## Why It Matters
## Learning Objectives
## Core Concepts
## Architecture
## How It Works
## Step-by-Step
## Example
## Enterprise Example
## Common Mistakes
## Troubleshooting
## Security Considerations
## Best Practices
## Key Takeaways
## Hands-on Exercise
## Completion Checklist
## References
```

Content must explain terminology in plain language, state assumptions, distinguish prototypes from
production, discuss trade-offs, and use primary sources for technical claims. Time-sensitive claims
must identify the relevant version or review date.

## Lab standard

Every implemented lab directory must contain:

```text
README.md
instructions.md
starter/
solution/
assets/
```

The instructions must cover objective, scenario, architecture, prerequisites, required tools,
difficulty, setup, build, test, validation, expected results, troubleshooting, challenge exercise,
enterprise extension, security, cleanup, and completion criteria.

A lab must be executable whenever the subject permits. It must include safe sample data, declared
versions, deterministic setup, and a way to verify the result. A screenshot or successful model
response alone is not completion evidence.

## Architecture and diagram rules

- Use Mermaid when a workflow, boundary, or decision is materially clearer as a diagram.
- Keep node names concise and define trust, authorization, and system-of-record boundaries.
- Accompany diagrams with prose describing failure behavior, observability, and ownership.
- Store source files for non-Mermaid diagrams under `assets/diagrams/` when that area is implemented.
- Do not copy proprietary diagrams or branding without explicit rights.

## Code and example rules

- Keep provider-neutral interfaces separate from provider adapters.
- Validate inputs and structured outputs at every external boundary.
- Use timeouts, bounded retries, idempotency, and safe error handling where applicable.
- Include tests for invalid, unauthorized, unavailable, and duplicate requests.
- Pin or constrain dependencies and document the supported runtime.
- Never fabricate benchmark results; record how measurements were produced.

## Security and data rules

Never commit:

- API keys, passwords, tokens, certificates, or connection strings with credentials;
- production customer data, confidential documents, or unredacted sensitive logs;
- private endpoints, tenant identifiers, or internal details without approval;
- model outputs containing sensitive data that is unnecessary for the learning objective.

Use [.env.example](.env.example) for variable names only. Use synthetic or explicitly approved data,
minimize collected context, apply least privilege, and include human approval for consequential
actions.

If a contribution appears to expose a secret or sensitive data, stop work, avoid copying the value,
and notify the repository owner through the approved private channel.

## Validation checklist

Before requesting review:

- [ ] The change is in scope for the active delivery phase.
- [ ] All relative Markdown links resolve.
- [ ] Mermaid blocks and executable examples have been validated.
- [ ] Setup and cleanup instructions work from a clean environment.
- [ ] Tests cover the relevant success and failure paths.
- [ ] No credentials, sensitive data, placeholders, or unexplained empty files are included.
- [ ] Security, enterprise trade-offs, and limitations are explicit.
- [ ] `git diff --check` and `git status` have been reviewed.
- [ ] The commit message follows the conventional format.

## Review criteria

Reviewers evaluate correctness, clarity, reproducibility, security, accessibility, maintainability,
and fit with the four-level maturity model. Review approval means the claims are supported and the
artifact is useful; it does not mean a particular tool or vendor is endorsed.
