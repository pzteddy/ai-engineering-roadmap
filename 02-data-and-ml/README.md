# Data and Machine Learning

This domain develops the judgment to build useful models from imperfect data and to distinguish a
real improvement from leakage, noise, or an inappropriate metric.

## Scope

- Data acquisition, schemas, profiling, cleaning, lineage, and quality checks.
- Descriptive statistics, probability, sampling, uncertainty, and experiment reasoning.
- Feature construction and reproducible preprocessing pipelines.
- Supervised and unsupervised learning with strong simple baselines.
- Split strategy, cross-validation, class imbalance, calibration, and threshold selection.
- Error analysis, subgroup performance, interpretability, drift, and communication of limitations.

## Expected outcomes

A learner can frame a prediction problem in terms of a real decision, construct a defensible dataset,
choose a baseline and evaluation design, compare candidate models, and explain both useful behavior
and material failure modes. They treat data and evaluation code as production assets rather than
disposable notebook state.

## Completion evidence

- A versioned data contract and automated quality checks.
- A reproducible pipeline from source data to features, training, and evaluation.
- Baseline and candidate results using a split and metrics justified by the decision context.
- Leakage analysis, threshold or calibration analysis where applicable, and representative errors.
- A model report covering intended use, limitations, subgroup behavior, and inference interface.

## Engineering bar

Reported metrics must be reproducible from a clean run and accompanied by enough context to interpret
them. Increasing complexity without a measured, decision-relevant benefit does not satisfy the exit
criteria.

Previous: [Engineering foundations](../01-engineering-foundations/README.md) ·
Next: [Deep learning](../03-deep-learning/README.md) ·
[Repository overview](../README.md)
