# Changes：Orca 测试工作树清理归档

> Inventory only. 判断在 task-card，证据在拆除核验与 control-check。

## 1. 概览

| 批次 | 提交 | 文件数 | 核心说明 |
| --- | --- | --- | --- |
| uncommitted | 未提交 | 8 | 补主目录工作树总控，并归档已拆除的三棵 Orca 测试树 |

## 2. 交付物清单

| 对象 | 类型 | 核心说明 |
| --- | --- | --- |
| `WORKTREE_TASKS.md` | 新增 | 主目录工作树总控；活树观察块由 control-check 对账 |
| `docs/worktree-control/index.json` | 新增 | 有界观察账本；不含机器绝对路径 |
| `docs/worktree-control/cleanup-260912-orca-tests.md` | 新增 | 已拆除三棵测试树的归档替代入口 |
| `docs/worktree-control/260912-paseo-probe.md` | 新增 | 仍在的 Paseo 探测树观察摘要 |
| `docs/worktree-control/settings-polish.md` | 新增 | 仍在的 settings-polish 观察摘要（含脏文件） |
| `vibe/specs/2609/260913/1005-orca-test-worktree-cleanup/task-card.md` | 新增 | 本轮清理与文档归档任务卡 |
| `vibe/specs/2609/260913/1005-orca-test-worktree-cleanup/changes.md` | 新增 | 本清单 |
| `vibe/specs/PROJECT_STATUS.md` | 改动 | 当前焦点与未清活树门禁 |

## 3. 逐批清单

### uncommitted

| 文件 | 核心说明 |
| --- | --- |
| `WORKTREE_TASKS.md` | 活树索引 + 链到清理归档 |
| `docs/worktree-control/*` | 观察摘要、账本、已拆树归档 |
| `vibe/specs/2609/260913/1005-orca-test-worktree-cleanup/*` | 任务卡与变更清单 |
| `vibe/specs/PROJECT_STATUS.md` | 枢纽同步 |

## 4. 明确没做的（分流，不是遗漏）

| 对象 | 数量 | 核心说明 |
| --- | --- | --- |
| `settings-polish` 拆除 | 1 | 有未提交 Settings 改动，未授权 |
| `grok/260912-paseo-probe` 拆除 | 1 | 未点名 |
| `vibe/knowledge/computer-use/**` | 3 | 无关脏文件，保持不动 |
| 提交 / 推送 | 0 | 本轮未授权 Git 写入远端或提交 |

## 5. 用户可见行为变化

| 位置 | 变化 | 核心说明 |
| --- | --- | --- |
| Orca AnyDrag 侧栏 | 三棵测试卡消失 | 此前 Orca rm 已完成；本轮补文档 |
| 仓库过程文档 | 新增总控与归档 | 后续清理走观察记录，不再只清 UI |
