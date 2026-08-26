# Engineering Foundations

Reliable AI systems inherit the strengths and weaknesses of the software around their models. This
domain establishes the delivery habits needed to turn experiments into systems other people can
run, test, review, and operate.

## Scope

- Python language fluency, packaging, environments, typing, errors, logging, and configuration.
- Git workflows, change review, shell usage, process behavior, and filesystem fundamentals.
- HTTP, API contracts, serialization, authentication boundaries, timeouts, and retries.
- Relational data modeling, SQL, transactions, migrations, and basic caching.
- Unit, integration, contract, and end-to-end testing with appropriate test doubles.
- Containers, continuous integration, dependency hygiene, and technical documentation.

## Expected outcomes

A learner can decompose a requirement into small changes, implement it as maintainable Python,
store and retrieve data safely, expose behavior through an API, and diagnose failures without
guessing. They understand which properties belong in code, tests, configuration, or operational
documentation.

## Completion evidence

- A packaged, typed Python service with a documented public interface.
- Automated tests covering logic, persistence, and at least one service boundary.
- A database migration and a reproducible local environment.
- Structured logs, safe configuration handling, and deliberate timeout/error behavior.
- A concise architecture note plus a Git history that can be reviewed commit by commit.

## Engineering bar

The artifact must run from a clean checkout using documented commands. Tests must fail for a known
behavioral regression, credentials must remain outside version control, and error responses must not
expose internal or sensitive data.

Previous: [Orientation](../00-orientation/README.md) ·
Next: [Data and machine learning](../02-data-and-ml/README.md) ·
[Repository overview](../README.md)
