# Level 2 Labs — Tools & Automation

The Level 2 track moves from information to controlled action through narrow tool contracts,
deterministic policy, and traceable execution.

## Planned lab sequence

| Lab | Capability | Verifiable result |
| --- | --- | --- |
| API call | Invoke a documented service safely | Timeouts, errors, and schema validation are tested |
| Function calling | Map model intent to a typed capability | Application—not model—decides whether to execute |
| MCP integration | Discover and invoke a bounded tool | Identity, scope, and authorization remain explicit |
| Database access | Read and update structured data | Least privilege, transactions, and unsafe-query controls |
| n8n AI workflow | Orchestrate events and services | Idempotent, observable workflow with failure path |
| UiPath AI workflow | Integrate with a legacy interface | Controlled RPA action, reconciliation, and audit evidence |

## Integrated mini-project

Build a tool-using assistant for a business workflow such as invoice status or service-request
routing. Separate read, validation, draft, approval, and execution capabilities; assign autonomy by
risk.

## Completion gate

- Every tool has a typed contract, owner, scope, timeout, and structured error model.
- Authorization, business validation, and risk checks happen outside model reasoning.
- High-impact or irreversible actions cannot execute without the defined control.
- Duplicate and partial-failure paths are tested and reconciled.
- Request, tool decision, execution result, and business outcome are traceable.

Previous: [Level 1 labs](../level-1/README.md) · Next: [Level 3 labs](../level-3/README.md)
