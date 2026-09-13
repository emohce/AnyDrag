# Task Card

> Standard non-requirement work only.

Tool: grok
Date: 2026-09-13
Task: 1005-orca-test-worktree-cleanup

## Task Documentation Sync Group

- Group key: `dsg:anydrag:1005-orca-test-worktree-cleanup`
- Group owner: this `task-card.md`
- Git document prefixes: `WORKTREE_TASKS.md`, `docs/worktree-control/`, `vibe/specs/`
- Durable document members: this card, `changes.md`, `PROJECT_STATUS.md`, `WORKTREE_TASKS.md`, `docs/worktree-control/*`
- Declared code/config dependencies: none
- Linked current/canonical/rule/memory authorities: worktree lifecycle, document archive disposition, project documentation adapter
- Excluded unrelated dirty documents: `vibe/knowledge/computer-use/**`, `vibe/knowledge/README.md` 既有 Computer Use 改动
- Lookup contract: `get --lookup-only` returns `present/freshness=unchecked`; only `check status=hit` may reuse the gate.

```json documentation-sync-group-v1
{
  "schema": "documentation-sync-group-v1",
  "group_key": "dsg:anydrag:1005-orca-test-worktree-cleanup",
  "group_owner": "vibe/specs/2609/260913/1005-orca-test-worktree-cleanup/task-card.md",
  "documents": [
    "vibe/specs/2609/260913/1005-orca-test-worktree-cleanup/task-card.md",
    "vibe/specs/2609/260913/1005-orca-test-worktree-cleanup/changes.md",
    "vibe/specs/PROJECT_STATUS.md",
    "WORKTREE_TASKS.md",
    "docs/worktree-control/index.json",
    "docs/worktree-control/cleanup-260912-orca-tests.md",
    "docs/worktree-control/260912-paseo-probe.md",
    "docs/worktree-control/settings-polish.md"
  ],
  "dependencies": [],
  "validators": [],
  "git_scope_prefixes": ["WORKTREE_TASKS.md", "docs/worktree-control", "vibe/specs"]
}
```

## Goal And Scope

- Goal: 拆除已授权的 Orca 测试工作树，并在主目录留下可恢复的归档与活树观察，而不是只清 Orca 侧栏。
- In scope: `porbeagle`、`260912-yin-yang-probe`、`给我测试一下这个Orca本身重命名的能力` 的 Git/Orca 拆除核验；建立 `WORKTREE_TASKS.md` 与清理归档。
- Out of scope: 清理 `settings-polish` 或 `grok/260912-paseo-probe`；提交/推送；纳管 lifecycle；改应用代码。
- Success evidence: 三棵测试树目录与本地分支不存在；归档记录列出拆除证据；`control-check` 覆盖剩余子树。

## Decision

- Documentation level: `standard`
- Execution: `main-only`
- Automation lane: `explicit-cli`（Orca `worktree rm`）
- Key decision and reason: 这些树没有既有任务卡可逻辑归档；默认 `archived-linked` 缺替代正文，故新建清理归档作为当前替代，不物理搬迁不存在的旧文。
- High-risk / DB boundary: none
- Plan-mode preflight completed before first edit: `yes`
- Plan artifact scope and documentation impact: `project-current`
- Verification map: absent — dynamic analysis
- Provisional `VerificationImpactTrace` completed before verification commands: `yes`
- Verification-command provenance: `impact-trace`
- Test additions/execution: impact-selected only

## Prior Task Overlap

- Relationship: `continuation`
- Prior authority and verified state: 本会话已拆除 `porbeagle` 与 `260912-yin-yang-probe`；D2 重命名树 Orca/Git 已拆除。`1356-ai-rules-init` 不覆盖工作树总控。
- Document governance: 主目录此前无 `WORKTREE_TASKS.md`；`control-check` 报 `control_records_missing` 与两棵活树 `worktree_not_indexed`。
- Execution logic verification / residual gates: `settings-polish` 仍脏，未授权拆除。
- Traceability and decision: `new-task`

## Documentation Realization

- Task and mechanism design authority: this card + [cleanup archive](../../../../docs/worktree-control/cleanup-260912-orca-tests.md)
- Requirement evolution / canonical merge authority: not applicable
- Intermediate problem / verified alternative / verification authority: Orca `worktree show/rm`、`git worktree list`、`git log origin/main..HEAD`
- Semantic execution account and unavailable-information boundary: 已拆除树的 Orca 元数据不再可读；以拆除当时的核验记录为准。

## Optimization And Template Propagation

- Optimization promotion: `not-applicable`
- Applied project/template impact: `none`
- Parent task / excluded roots: none

## Rule Task Trace

- Registry scope: `project-local / not-admitted`
- Registry identity / row: none
- Requirement and implementation authority: this card
- Propagation / delegation / Root acceptance: project-current hubs only

## Work And Verification

- Changed surface: Orca/Git 工作树拆除；主目录工作树总控与过程枢纽
- Verification: `git worktree list`、分支列表、目录 `ls`、`orca worktree list`、`control-check`
- Unverified gaps: `settings-polish` 脏文件含义；Paseo 树是否仍要保留
- Delegated read-only result and Root decision, if any: none

### Verification Decision

- Route: `focused-automated`
- Reason: 拆除与总控可见性可用 Git/Orca/control-check 核验；无 UI 产品行为
- Impact source and freshness: live Git/Orca 2026-09-13
- Plan verification clauses reconciled before execution: `not-applicable`
- Affected modules / boundaries: Git worktree inventory；Orca workspace list；docs/worktree-control
- Checked: 三棵测试树路径/分支不存在；剩余两棵子树已观察
- Skipped: 应用构建、Accessibility
- Full-suite escalation: `none`
- Owner: this card
- Residual risk: 只清 Orca 展示会丢归档；本轮已补文档

### Verification Impact Trace

| Changed surface / claim | Direct consumers | Material transitive or failure boundary | Selected evidence | Skipped suites / reason | Outcome / residual |
| --- | --- | --- | --- | --- | --- |
| 三棵测试树已拆除 | Orca 侧栏、Git worktree 清单 | 误删有独有提交的树 | `git log origin/main..HEAD` 空；`ls` 不存在；`orca worktree list` 无对应卡 | 产品构建：无应用代码 | pass |
| 主目录总控可见性 | `WORKTREE_TASKS.md`、后续清理 | 漏记活树会再次只清 UI | `worktree_task.py control-check` | lifecycle 纳管：未授权 | 见 closeout |

## Authority Packet And Documentation Impact

- Authority refs read: worktree-tasks §2.1/§6, document archive disposition, project documentation.md, manage-worktree-task status-and-resume
- Decisive source evidence: Orca rm `removed: true`；Git 清单与分支列表
- `doc_drift`: `resolved`（展示已拆、文档原先缺失）
- Document impact: `project-current`
- Synchronized authorities and verification: PROJECT_STATUS、WORKTREE_TASKS、docs/worktree-control、this card
- Root acceptance gate: `accepted`（可见性已对账；两棵活树 `task_owner_unconfirmed` 是记录缺口，不是漏索引）

## Execution Journal

| Event ID | Local Time | Work Unit / Attempt | Actor / Surface | Event | Prior -> Resulting State | Trigger / Evidence | Root Decision / Next Action |
| --- | --- | --- | --- | --- | --- | --- | --- |
| E1 | 2026-09-12 | cleanup-porbeagle | orca-cli | 拆除 porbeagle | 测试树 -> 已拆除 | 干净、无独有提交 | 继续 |
| E2 | 2026-09-12 | cleanup-yin-yang | orca-cli | 拆除 260912-yin-yang-probe | 探测树 -> 已拆除 | 干净、无独有提交 | 继续 |
| E3 | 2026-09-13 | cleanup-d2 | orca-cli | 拆除重命名测试树 | Orca/Git 已拆、文档仍缺 | path 选择器 rm | 补归档 |
| E4 | 2026-09-13 10:05 | docs-archive | main | 建立总控与清理归档 | 无 WORKTREE_TASKS -> 有观察+历史 | 用户要求文档归档删除 | control-check |

## Efficiency / Token Evidence

| Metric | Baseline | Observed | Delta | Confidence / Source |
| --- | --- | --- | --- | --- |
| not applicable |  |  |  | usage unavailable |

## TaskExperienceObservation

- Result: `not applicable`
- Control score / observed dimensions:
- Failed / unavailable dimensions:
- Promotion decision: `not applicable`

## Implementation Sync

- Authoritative current behavior: 已拆除树只存在于 [cleanup archive](../../../../docs/worktree-control/cleanup-260912-orca-tests.md)；活树见 [WORKTREE_TASKS.md](../../../../WORKTREE_TASKS.md)
- Module / document mapping: Orca workspace ≠ 仓库总控；拆除必须双写
- Evidence or `not applicable`: control-check 与 Git 清单

## Closeout

- Sidecar: `main-thread`
- Requirement / business / tech route: process / worktree-control
- Unresolved gates: `settings-polish` 与 `260912-paseo-probe` 未授权清理
- Next action: 用户若要继续清 D1/D3，先核 `settings-polish` 脏 Settings 源码
