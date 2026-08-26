# LLM Engineering

This domain covers applications built around large language models, with evaluation and bounded
behavior as first-class design concerns. Prompt text is one component; the engineered system also
includes data, retrieval, tools, control flow, validation, and operations.

## Scope

- Model capabilities, tokenization, context limits, sampling, and provider selection.
- Instruction design, structured outputs, schema validation, and model-facing contracts.
- Embeddings, chunking, indexing, retrieval, reranking, grounding, and citation behavior.
- Tool interfaces, workflow orchestration, state, memory boundaries, and agent control loops.
- Fine-tuning and adaptation decisions relative to prompting and retrieval.
- Evaluation sets, graders, human review, failure taxonomies, and regression testing.
- Prompt injection, data exfiltration, unsafe actions, permissioning, and execution limits.

## Expected outcomes

A learner can decide whether an LLM is appropriate, design the smallest effective model interaction,
and measure the complete task rather than isolated fluency. They can distinguish retrieval,
generation, tool, and orchestration failures and improve the correct layer.

## Completion evidence

- A versioned representative evaluation set with explicit task success criteria.
- A simple baseline and an improved system whose change is supported by measured results.
- Validated structured outputs and bounded failure behavior.
- Stage-level retrieval evaluation when external knowledge is required.
- A threat model, adversarial tests, latency distribution, and per-task cost estimate.

## Engineering bar

Subjective demo quality cannot substitute for evaluation. Agentic behavior must earn its additional
latency, cost, and risk, and tools must use least privilege with explicit input validation and limits.

Previous: [Deep learning](../03-deep-learning/README.md) ·
Next: [Production AI](../05-production-ai/README.md) ·
[Repository overview](../README.md)
