# AnyDrag 工作树总控

覆盖当前 Git common-directory 的全部子工作树。主目录保留观察摘要；未证实的任务归属保持 `unconfirmed`。已拆除的 Orca 测试树不进入观察块，以免 `indexed_worktree_missing`；历史见 [清理归档](docs/worktree-control/cleanup-260912-orca-tests.md)。

<!-- worktree-control-observations:start -->
| 任务与主目录记录 | 进度 / 保留 | 核心规划 | 下一步 / 恢复条件 | 标记 |
| --- | --- | --- | --- | --- |

[Git、规划摘要与缓存引用记录](docs/worktree-control/index.json#L1)
<!-- worktree-control-observations:end -->

核验：`python3 <CodeNote>/AiRef/VibePractice/Skills/global/manage-worktree-task/scripts/worktree_task.py control-check --control-repo <AnyDrag主目录>`。`indexed-current` 只表示有限观察一致；`unmanaged` 不等于已纳管。`retained` 仅表示目录保留。

## 已拆除（不在 Git 清单）

详见 [cleanup-260912-orca-tests.md](docs/worktree-control/cleanup-260912-orca-tests.md)。`porbeagle`、`260912-yin-yang-probe`、`给我测试一下这个Orca本身重命名的能力`、`grok/260912-paseo-probe`、`settings-polish` 已拆除。`settings-polish` 的 Settings 打磨已合入 `czz-dev`。后续 清理 默认含本地分支，见 CodeNote [worktree-tasks §6](../../CzzProj/CodeNote/AiRef/VibePractice/Vibe_Rules/process/worktree-tasks.md#6-integration-and-cleanup)；仅当当前消息写明只清理 Orca 时才留分支。
