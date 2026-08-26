# Datasets

This area will contain synthetic sample data and versioned evaluation datasets used by examples and
labs. No production customer data or confidential document may be committed here.

## Planned layout

| Area | Purpose |
| --- | --- |
| `sample/` | Small synthetic inputs for demonstrations and local tests |
| `evaluation/` | Curated cases for repeatable quality, safety, and regression evaluation |

Local `raw/`, `private/`, and generated data directories are excluded by [.gitignore](../.gitignore).

## Dataset contract

Each committed dataset must document:

- purpose, owner, maturity level, and supported task;
- origin or generation method and redistribution rights;
- schema, field meanings, encoding, and stable case identifiers;
- data classification, redaction or synthesis method, and prohibited uses;
- normal, edge, known-failure, high-risk, and adversarial coverage;
- expected outputs or scoring rules and acceptable variation;
- version, change history, known limitations, and review date.

## Safety rules

- Prefer generated data that cannot be mistaken for real people or accounts.
- Never commit credentials, private endpoints, production identifiers, or sensitive logs.
- Minimize fields to what the learning objective requires.
- Scan samples and model outputs for accidental sensitive content before committing.
- Do not use synthetic data to claim real-world fairness or production performance.

[Repository overview](../README.md) ·
[Level 3 evaluation contract](../docs/03_Evaluation_Reliability_Scale/README.md)
