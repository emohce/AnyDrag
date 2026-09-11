# AnyDrag Project Status

Tool: grok
Date: 2026-09-11

## Purpose

Compact process hub for active AI work. This file routes current tasks to project docs without storing durable rules.

## Rule Links

- Project documentation: [../rules/documentation.md](../rules/documentation.md)
- Project knowledge: [../knowledge/README.md](../knowledge/README.md)
- Global process rules: [../../../../CzzProj/CodeNote/AiRef/VibePractice/Vibe_Rules/process/rules.md](../../../../CzzProj/CodeNote/AiRef/VibePractice/Vibe_Rules/process/rules.md#3-project-location)

## Current Focus

- Status: fork cloned to `GitFork/AnyDrag`; local working branch is `czz-dev` from `origin/main` `9eb03c93` (CalVer `26.09.114`). CodeNote AI rule chain initialized. No application code changed.
- Latest task docs: [task card](2609/260911/1356-ai-rules-init/task-card.md), [changes](2609/260911/1356-ai-rules-init/changes.md).
- Remotes: `origin=emohce/AnyDrag`，`upstream=XueshiQiao/AnyDrag`. `czz-dev` is local-only; not pushed. 误造的 `CzzRef/AnyDrag` 远端已不存在；本地 GitFork 目录保留。
- CodeNote catalog: `project-index.json` + this-host `workspace.local.json` binding.

## Active Task Index

| Task | Status | Authoritative Doc | Verification | Notes |
| --- | --- | --- | --- | --- |
| AI rules init | `implemented-local / gitfork-local-committed / unpushed` | [task-card](2609/260911/1356-ai-rules-init/task-card.md) | project audit 仅余官方短入口 inherited | `2ee37f5`；未推送 |
| origin 改回 emohce | `corrected-local / czzref-remote-absent` | CodeNote [1451](../../../../CzzProj/CodeNote/vibe/specs/2609/260911/1451-gitfork-land-existing-origin/task-card.md) | `git ls-remote origin` → `9eb03c93` | 保留 `GitFork/AnyDrag` |

## Verification State

- Last verified: 2026-09-11 (docs/rules)
- Commands: CodeNote `audit_ai_rules.py --mode project`；authored-file code-link audit
- Unverified gaps: `xcodegen generate`、Xcode 构建、Accessibility 真机手势、Sparkle、CI 公证
- Latest Sidecar result: not applicable — onboard path already verified
- Latest Prior Task Overlap: reference-only GitFork/react-doctor adapter shape; decision `new-task`
- Latest Documentation Impact: `project-current`
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
|  |  |  |  | no-pending |

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
