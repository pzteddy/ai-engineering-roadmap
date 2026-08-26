# Repository Scripts

This area will hold cross-platform automation for environment setup, validation, tests, and
evaluation. Phase 1 defines the script contract; it does not ship nonfunctional shell files merely to
fill the planned tree.

## Planned entry points

| Script | Responsibility |
| --- | --- |
| `setup.sh` | Prepare and verify supported Unix-like development environments |
| `setup.ps1` | Prepare and verify supported PowerShell development environments |
| `run_tests.py` | Run deterministic unit, integration, contract, and content checks |
| `evaluate.py` | Execute versioned AI evaluations and produce machine-readable results |

## Script contract

Implemented scripts must:

- fail clearly and return a non-zero exit code on error;
- avoid printing secrets or sensitive input;
- be safe to rerun and avoid destructive defaults;
- support documented dry-run behavior for external mutations;
- accept configuration through validated arguments or environment variables;
- pin or check required versions and declare network or account dependencies;
- write generated artifacts only to documented ignored paths;
- provide cleanup for resources they create.

Evaluation output should include dataset, prompt, model, retrieval, tool, policy, and code versions
needed to reproduce the run, without recording credential values.

[Repository overview](../README.md) · [Contributing standard](../CONTRIBUTING.md)
