# Agent Reliability Lab

**Twelve small, deterministic tools for testing and hardening AI agent infrastructure.**

Each package is a dependency-light Python core with tests, examples and an explicit failure model. Use one, or use all of them. Together they cover what usually breaks once an agent leaves the demo: tool contracts, transports, trust boundaries, replay, scheduling and evals.

Part of the [proof layer for AI agents](https://yashkhou.com) together with [RunLedger](https://github.com/yashkhou/runledger), [BrowserProof](https://github.com/yashkhou/browserproof), [ActionMesh](https://github.com/yashkhou/actionmesh) and [Verify](https://github.com/yashkhou/verify).

## Packages

| Package | Reliability boundary |
| --- | --- |
| [`context-firewall`](packages/context-firewall) | Provenance-aware trust boundaries and fail-closed checks before privileged tool calls. |
| [`tool-contract-fuzzer`](packages/tool-contract-fuzzer) | Deterministic valid/invalid JSON-Schema cases, boundary mutations and shrinking. |
| [`mcp-chaos`](packages/mcp-chaos) | Deterministic JSON-RPC / MCP fault injection and wire-level chaos testing. |
| [`agent-replay`](packages/agent-replay) | Redacted, hash-chained agent event logs with integrity-aware deterministic replay. |
| [`failure-corpus`](packages/failure-corpus) | Normalise, fingerprint and deduplicate CI and agent failures into regression corpora. |
| [`handoff-spec`](packages/handoff-spec) | Canonical, digestible handoffs for resumable long-running agents. |
| [`toolgraph-profiler`](packages/toolgraph-profiler) | Critical paths, retries, fan-out, lock pressure and idle time in tool-call traces. |
| [`agent-policy-compiler`](packages/agent-policy-compiler) | Explainable policy-as-code for deterministic allow/deny decisions on agent actions. |
| [`eval-capsule`](packages/eval-capsule) | Portable eval fixtures, assertions and integrity-checked reproducible archives. |
| [`schema-evolution-guard`](packages/schema-evolution-guard) | CI checks for compatibility-breaking changes in evolving tool schemas. |
| [`context-budgeter`](packages/context-budgeter) | Token allocation, duplicate detection and policy-collision analysis for context bundles. |
| [`agent-scheduler-sim`](packages/agent-scheduler-sim) | Discrete-event simulation of worker, retry and starvation behaviour in agent queues. |

## Install a package

```sh
pip install "git+https://github.com/yashkhou/agent-reliability-lab#subdirectory=packages/mcp-chaos"
```

Every package needs Python 3.11+ and has no runtime dependencies.

## Develop

```sh
cd packages/context-firewall
PYTHONPATH=src python -m unittest discover -s tests -v
```

CI runs all twelve test suites on Python 3.11, 3.12 and 3.13.

## History

Each package started as its own repository. They were merged here with `git subtree`, so every commit is preserved, and the original repositories are archived with a pointer to this one.

## License

MIT
