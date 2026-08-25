# DIKWP AgentTrace OS

[English documentation](#why-this-matters) · [中文速览](#中文速览) · [Download the release package](./dikwp_agenttrace_os_open_source_app.zip)

> **Release layout / 发布结构** — The runnable source is distributed in `dikwp_agenttrace_os_open_source_app.zip`. Download and extract the package first, enter the extracted application directory, and then run the commands in **Quick start**. / 可运行源码位于上述 ZIP 发布包中；请先下载并解压，进入解压后的应用目录，再执行下方命令。

## 中文速览

- **它解决什么问题**：把一次 AI Agent 运行转换为防篡改的 DIKWP 语义追踪账本，记录观察、决策、工具调用、记忆写入、证据与风险事件。
- **适合谁**：Agent 开发者、AI 安全与治理团队、模型评测人员，以及需要事故回放和证据保全的研究者。
- **如何开始**：下载并解压发布包，在应用目录中完成本地安装，然后使用示例运行生成时间线、风险事件、证据账本与回放包。
- **使用边界**：本项目用于经过授权的 AI 系统审计，不用于隐蔽监控人员；实际部署应包含告知、目的限制、脱敏、访问控制、保留期限和人工复核。

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
