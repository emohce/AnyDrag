# AnyDrag Project Status

Tool: grok
Date: 2026-09-13

## Purpose

Compact process hub for active AI work. This file routes current tasks to project docs without storing durable rules.

## Rule Links

- Project documentation: [../rules/documentation.md](../rules/documentation.md)
- Project knowledge: [../knowledge/README.md](../knowledge/README.md)
- Global process rules: [../../../../CzzProj/CodeNote/AiRef/VibePractice/Vibe_Rules/process/rules.md](../../../../CzzProj/CodeNote/AiRef/VibePractice/Vibe_Rules/process/rules.md#3-project-location)

## Current Focus

- Status: 已拆除三棵无独有提交的 Orca 测试工作树，并补主目录总控/归档；应用代码仍未改。`czz-dev` 基于 `origin/main` `9eb03c93`（CalVer `26.09.114`）。
- Latest task docs: [清理归档任务卡](2609/260913/1005-orca-test-worktree-cleanup/task-card.md), [changes](2609/260913/1005-orca-test-worktree-cleanup/changes.md)。规则初始化仍见 [1356 task card](2609/260911/1356-ai-rules-init/task-card.md)。
- Worktree control: [WORKTREE_TASKS.md](../../WORKTREE_TASKS.md)；已拆树归档 [cleanup-260912-orca-tests.md](../../docs/worktree-control/cleanup-260912-orca-tests.md)。
- Remotes: `origin=emohce/AnyDrag`，`upstream=XueshiQiao/AnyDrag`. `czz-dev` is local-only; not pushed. 误造的 `CzzRef/AnyDrag` 远端已不存在；本地 GitFork 目录保留。
- CodeNote catalog: `project-index.json` + this-host `workspace.local.json` binding.

## Active Task Index

| Task | Status | Authoritative Doc | Verification | Notes |
| --- | --- | --- | --- | --- |
| AI rules init | `implemented-local / gitfork-local-committed / unpushed` | [task-card](2609/260911/1356-ai-rules-init/task-card.md) | project audit 仅余官方短入口 inherited | `2ee37f5`；未推送 |
| origin 改回 emohce | `corrected-local / czzref-remote-absent` | CodeNote [1451](../../../../CzzProj/CodeNote/vibe/specs/2609/260911/1451-gitfork-land-existing-origin/task-card.md) | `git ls-remote origin` → `9eb03c93` | 保留 `GitFork/AnyDrag` |
| Orca 测试树清理 | `docs-uncommitted / git-removed` | [1005 task-card](2609/260913/1005-orca-test-worktree-cleanup/task-card.md) | `control-check` 覆盖剩余子树 | 三棵测试树已拆；文档未提交 |

## Verification State

- Last verified: 2026-09-13 (worktree inventory + control-check)
- Commands: `git worktree list`；`orca worktree list`；`worktree_task.py control-check`
- Unverified gaps: `xcodegen generate`、Xcode 构建、Accessibility 真机手势、Sparkle、CI 公证；`settings-polish` 脏 Settings 源码含义
- Latest Sidecar result: not applicable — onboard path already verified
- Latest Prior Task Overlap: reference-only GitFork/react-doctor adapter shape; decision `new-task`
- Latest Documentation Impact: `project-current`（工作树总控与清理归档）
- Latest Efficiency / Token Evidence: `usage unavailable`

## Open Risk Or Deploy Gates

- Gate: Developer ID 公证 / Sparkle 发布 / Homebrew tap / `bump-version.sh --push`
- Blocking condition: this task does not authorize live Accessibility experiments or publish
- Rollback note: `czz-dev` 仅含上游 `9eb03c93` 加本仓 AI 规则初始化；未推送

## Governance Baseline

- Template propagation: accepted global baseline; this project keeps only project-specific routes and does not copy mother-board rules.
- Codex evolution: `v3-route-accepted`; no Hook, supervisor, or rollout change in this repository.
- Rule Task Trace: accepted global baseline; this initialization is project-local and does not add a CodeNote registry row.
- `w24-primary-objective-continuity-accepted`: primary user work remains ahead of advisory governance lanes.
- `w28-documentation-impact-accepted`: this round synchronized project-current adapters/hubs.
- `w30-standard-requirement-owner-accepted`: Standard requirement ownership remains raw requirement plus the Spec owner; this task is Standard non-requirement (task card).

## Pending Follow-ups

| Item | Source turn / task | Owner | Next gate | Status |
| --- | --- | --- | --- | --- |
| `settings-polish` 仍保留 | 本轮清理 | 用户 | 确认脏 Settings 去向后再清或纳管 | open |
| `grok/260912-paseo-probe` 仍保留 | 本轮清理 | 用户 | 点名后再清或纳管 | open |

## Memory Routing

- Task rule declaration: recorded on the task card
- Sidecar document route: main-thread
- Prior Task Overlap: GitFork/react-doctor
- Evolution Candidate: none
- Project rules: created this round
- Knowledge: architecture map created this round
- ADR: empty index only
- Error memory: empty index
- DB memory: not configured

## Cross-Repository Links

| Concern | Repository | Status Hub |
| --- | --- | --- |
| Rule kernel / catalog | CodeNote | CodeNote `vibe/knowledge/project-index.json` |
| Auto onboard skill | CodeNote | `AiRef/VibePractice/Skills/global/onboard-czz-fork/` |

## Next Update Trigger

Update this hub when current focus, active task docs, verification status, open gates, sibling links, or memory routing changes.
