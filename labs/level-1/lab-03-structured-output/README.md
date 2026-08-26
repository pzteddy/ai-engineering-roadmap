# Lab 03 — Produce and Validate Structured JSON

Use the OpenAI Chat Playground to extract synthetic service requests into a fixed JSON contract.
Compare a vague JSON request with a schema-driven prompt and one example that demonstrates missing
data behavior.

Prompting for JSON is useful for learning, but production systems should use schema-constrained
Structured Outputs where supported and still handle refusals, truncation, and downstream
validation. A few-shot example can clarify semantics; it is not a substitute for validation.

## Learning outcomes

After this lab, you can:

- define required keys, types, enumerations, and missing-value behavior;
- decide when one example clarifies a schema boundary;
- distinguish valid JSON from schema-valid business data;
- test normal, incomplete, and instruction-like inputs;
- explain why production code must validate before automation.

## Scenario

An RPA engineer is prototyping service-request extraction. The model returns a proposal for human
review; no ticket is created and no workflow runs.

## Evidence produced

- baseline and final prompt versions;
- raw output for three synthetic requests;
- JSON syntax and contract-validation results;
- a list of remaining production controls.

## Lab files

- [Detailed instructions](instructions.md)
- [Starter prompt](starter/prompt.md)
- [Reference solution](solution/README.md)
- [Output contract](assets/output-contract.md)
- [Synthetic requests and answer key](assets/requests.md)

## Support boundary

This lab demonstrates response design in the Playground. It does not claim that a prompt alone
guarantees schema adherence, and it does not connect to a service desk or RPA platform.

[Previous lab](../lab-02-role-context/README.md) · [Back to Level 1 labs](../README.md)
