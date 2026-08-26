# Examples

This area will contain small, focused examples that illustrate one engineering decision at a time.
Examples support the curriculum; they are not substitutes for complete labs or production-ready
reference applications.

## Planned categories

| Category | Intended content |
| --- | --- |
| `prompts/` | Versioned prompt and context patterns with evaluation cases |
| `python/` | Provider-neutral Python interfaces, validation, and tests |
| `javascript/` | Provider-neutral JavaScript/TypeScript integrations |
| `api/` | REST contracts, authentication boundaries, timeouts, and errors |
| `mcp/` | Bounded MCP tools, resources, prompts, and authorization examples |
| `rag/` | Retrieval, reranking, grounding, citation, and evaluation examples |
| `agents/` | Deterministic and agentic workflows with guardrails and traces |

## Example contract

Every implemented example must identify its purpose, maturity level, prerequisites, supported
versions, execution command, expected behavior, failure behavior, and security limitations. It must
use synthetic inputs, contain no real credentials, and include a verification method.

Provider-specific code belongs in a clearly named adapter or subdirectory. The surrounding example
must explain the portable concept so that a learner can compare implementations without mistaking a
vendor API for the architecture itself.

Examples that perform state-changing actions must default to a safe local or dry-run mode and require
explicit configuration for external execution.

[Repository overview](../README.md) · [Contributing standard](../CONTRIBUTING.md)
