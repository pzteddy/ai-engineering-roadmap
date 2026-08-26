# Deep Learning

Deep learning is treated here as an engineering system whose behavior emerges from data,
architecture, optimization, and compute—not as a catalog of network diagrams.

## Scope

- Tensors, vectorization, automatic differentiation, computational graphs, and gradients.
- Training loops, initialization, optimization, schedules, batching, and regularization.
- Validation, checkpoints, experiment tracking, and reproducibility limits.
- Convolutional, sequential, attention-based, and transformer architectures at a systems level.
- Embeddings, transfer learning, adaptation, and representation analysis.
- Accelerator memory, mixed precision, throughput, and input-pipeline performance.

## Expected outcomes

A learner can implement and instrument a training pipeline, recognize common failure patterns, and
select an adaptation strategy that respects data and compute constraints. They can explain what a
framework is doing on their behalf and inspect the relevant intermediate signals when it fails.

## Completion evidence

- A training pipeline with configuration, deterministic controls, validation, and checkpoints.
- Recorded learning curves, resource measurements, and at least one controlled ablation.
- Diagnosis of an intentionally or naturally failed run based on evidence.
- An adapted pretrained model compared with a simple baseline.
- A behavior and limitations report that includes compute and data provenance.

## Engineering bar

A single successful training run is not enough. The learner must be able to reproduce it within
documented tolerances, recover it, explain its resource profile, and investigate a degradation
systematically.

Previous: [Data and machine learning](../02-data-and-ml/README.md) ·
Next: [LLM engineering](../04-llm-engineering/README.md) ·
[Repository overview](../README.md)
