# DIKWP AgentTrace OS

Open-source AI Agent black-box recorder, semantic trace ledger, and incident replay toolkit.

DIKWP AgentTrace OS turns an AI agent run into a tamper-evident semantic trace ledger. It helps teams answer:

- What did the agent see?
- What did it decide?
- What tool did it call?
- What memory did it write?
- Which evidence supported the final output?
- Where did intention drift, prompt injection, tool overreach, or evidence gaps appear?
- Can the run be replayed and reviewed without trusting the model's story after the fact?

The project is designed as part of the DIKWP open-source ecosystem. It complements:

- DIKWP AnswerGraph Studio: AI answer asset readiness.
- DIKWP IntentGuard OS: pre-execution intent firewall.
- DIKWP MemoryLedger OS: long-term memory governance.
- DIKWP SemanticEnergy OS: semantic cost and energy accounting.
- DIKWP ProofLedger OS: claim-to-evidence auditing.

AgentTrace OS fills the missing runtime layer: **agent observability, semantic forensics, and replayable audit custody.**

## Why this matters

Agentic AI systems are no longer simple chatbots. They call tools, retrieve context, write memory, delegate tasks, and act across multiple steps. Ordinary logs show raw events; they do not preserve DIKWP semantics, intention continuity, evidence custody, or replayable accountability.

AgentTrace OS provides a local, dependency-light prototype for:

- AI agent flight recording.
- Run-level semantic hash chains.
- Tool-call incident timelines.
- P-layer intention drift detection.
- Memory-write and prompt-injection risk detection.
- Evidence gap and unsupported claim detection.
- Replay bundle generation.
- OpenTelemetry-style span export.

## Quick start

```bash
pip install -e .
dikwp-agenttrace analyze examples/sample_agent_run.json --policy configs/default_policy.json --out outputs/demo
```

Run static boundary audit:

```bash
dikwp-agenttrace static-audit src --out outputs/demo/static_boundary_audit_report.json
```

## Output files

The demo command generates:

- `agent_trace_report.json`
- `trace_timeline.csv`
- `risk_events.csv`
- `dikwp_event_ledger.json`
- `replay_bundle.json`
- `otel_style_spans.json`
- `incident_recommendations.md`

## Design principle

DIKWP AgentTrace OS is not a surveillance tool for covertly monitoring people. It is a governance tool for auditable AI systems. It should be deployed with notice, purpose limitation, redaction, access control, retention limits, and human review.

## Attribution

DIKWP is attributed to Yucong Duan / Duan DIKWP Lab in this open-source prototype. See `NOTICE` and `CITATION.cff`.
