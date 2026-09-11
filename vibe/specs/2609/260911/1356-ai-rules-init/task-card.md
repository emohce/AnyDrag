# Task Card

> Standard non-requirement work only.

Tool: grok
Date: 2026-09-11
Task: 1356-ai-rules-init

## Task Documentation Sync Group

- Group key: `dsg:anydrag:1356-ai-rules-init`
- Group owner: this `task-card.md`
- Git document prefixes: `AGENTS.md`, `CLAUDE.md`, `vibe/`
- Durable document members: adapters, `vibe/rules/*`, `vibe/specs/*`, `vibe/knowledge/*`; CodeNote `vibe/knowledge/project-index.json` and ignored `workspace.local.json`
- Declared code/config dependencies: none (read-only on application source)
- Linked current/canonical/rule/memory authorities: CodeNote starter-kit, configure-agent-ecosystem project-rules, GitFork/react-doctor adapter shape, this hub
- Excluded unrelated dirty documents: CodeNote mixed dirty tree except the catalog row for this project
- Lookup contract: `get --lookup-only` returns `present/freshness=unchecked`; only `check status=hit` may reuse the gate.

```json documentation-sync-group-v1
{
  "schema": "documentation-sync-group-v1",
  "group_key": "dsg:anydrag:1356-ai-rules-init",
  "group_owner": "vibe/specs/2609/260911/1356-ai-rules-init/task-card.md",
  "documents": [
    "AGENTS.md",
    "CLAUDE.md",
    "vibe/rules/README.md",
    "vibe/rules/local-context.md",
    "vibe/rules/project.md",
    "vibe/rules/workflow.md",
    "vibe/rules/knowledge.md",
    "vibe/rules/documentation.md",
    "vibe/specs/README.md",
    "vibe/specs/PROJECT_STATUS.md",
    "vibe/specs/2609/260911/1356-ai-rules-init/task-card.md",
    "vibe/specs/2609/260911/1356-ai-rules-init/changes.md",
    "vibe/knowledge/README.md",
    "vibe/knowledge/architecture.md",
    "vibe/knowledge/adr/README.md",
    "vibe/knowledge/error-memory/README.md"
  ],
  "dependencies": ["project.yml", "AGENTS.md"],
  "validators": [],
  "git_scope_prefixes": ["AGENTS.md", "CLAUDE.md", "vibe"]
}
```

## Goal And Scope

- Goal: 把 `CzzRef/AnyDrag` 落到 GitFork，建立 `czz-dev`，并初始化 CodeNote adapter/rule/knowledge/process 链，供后续改造。
- In scope: GitHub fork；clone；`origin`/`upstream`；本地 `czz-dev`；短入口；`vibe/rules`；`vibe/knowledge`；`vibe/specs`；CodeNote catalog + 本机 binding；project-rules 发布；初始化后本地提交。
- Out of scope: 应用代码改造；Xcode 构建/公证；Accessibility 真机实验；push；把 `vibe/` 送到 `upstream`；Home/Hook/MCP 本机 apply。
- Success evidence: checkout 在 `czz-dev`；project audit 绿灯或仅余官方短入口 inherited findings；resolver `--project anydrag` 命中本 clone。

## Decision

- Documentation level: `standard`
- Execution: `main-only`
- Automation lane: `not-applicable`
- Key decision and reason: 用户给出的 `emohce/AnyDrag` 不是声明 fork owner；核验后它与上游 `XueshiQiao/AnyDrag@main` 完全一致。按 `onboard-czz-fork` 在 `CzzRef` 建 fork，`upstream` 指向真正来源仓。不复制 VibeAi 正文；不启用 intent-note、design-preference、AI-DB。
- High-risk / DB boundary: 无 SQL。CGEventTap / Accessibility / CI 签名材料只记录为禁区，本轮不触碰。
- Plan-mode preflight completed before first edit: `yes`
- Plan artifact scope and documentation impact: `project-current`
- Verification map: absent — static analysis
- Provisional `VerificationImpactTrace` completed before verification commands: `yes`
- Verification-command provenance: `impact-trace`
- Test additions/execution: impact-selected only; no separate user enumeration required

## Prior Task Overlap

- Relationship: `reference-only`
- Prior authority and verified state: GitFork/react-doctor `260908/1302-ai-rules-init` 已编码下游 adapter 形状；`mac_dock_command` 是同类 macOS GitFork。
- Document governance: 本仓库有官方 `AGENTS.md` / `CLAUDE.md`，初始化前无 `vibe/` 树。
- Execution logic verification / residual gates: CodeNote catalog 无 `anydrag` 行。
- Traceability and decision: `new-task` with template delta (do not rerun those migrations).

## Documentation Realization

- not applicable (initialization, not a runtime/rule correction)

## Optimization And Template Propagation

- Optimization promotion: `not-applicable`
- Applied project/template impact: `none`
- Parent task / excluded roots: CodeNote 既有脏文件不纳入本轮
