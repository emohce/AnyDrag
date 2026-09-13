# AnyDrag 工作树总控

覆盖当前 Git common-directory 的全部子工作树。主目录保留观察摘要；未证实的任务归属保持 `unconfirmed`。已拆除的 Orca 测试树不进入观察块，以免 `indexed_worktree_missing`；历史见 [清理归档](docs/worktree-control/cleanup-260912-orca-tests.md)。

<!-- worktree-control-observations:start -->
| 任务与主目录记录 | 进度 / 保留 | 核心规划 | 下一步 / 恢复条件 | 标记 |
| --- | --- | --- | --- | --- |
| [260912-paseo-probe](docs/worktree-control/260912-paseo-probe.md) | unmanaged-observation / clean-retained / retained | Paseo 探测树；执行归属未证实，不自动绑定 | 用户点名后再决定清理或纳管；先确认任务归属，再授权拆除或 adopt | `2ad2027ccb7580d7` |
| [settings-polish](docs/worktree-control/settings-polish.md) | unmanaged-observation / child-dirty-retained / retained | Orca settings 树；执行归属未证实，有未提交 Settings 改动 | 用户点名后再核脏文件去向或清理；先确认归属和脏 Settings 源码，再授权拆除或纳管 | `453ee00c9dd716ef` |

[Git、规划摘要与缓存引用记录](docs/worktree-control/index.json#L1)
<!-- worktree-control-observations:end -->

核验：`python3 <CodeNote>/AiRef/VibePractice/Skills/global/manage-worktree-task/scripts/worktree_task.py control-check --control-repo <AnyDrag主目录>`。`indexed-current` 只表示有限观察一致；`unmanaged` 不等于已纳管。`retained` 仅表示目录保留。

## 已拆除（不在 Git 清单）

详见 [cleanup-260912-orca-tests.md](docs/worktree-control/cleanup-260912-orca-tests.md)。`porbeagle`、`260912-yin-yang-probe`、`给我测试一下这个Orca本身重命名的能力` 已从 Orca 与 Git 拆除，无独有提交。后续 清理 默认含本地分支，见 CodeNote [worktree-tasks §6](../../CzzProj/CodeNote/AiRef/VibePractice/Vibe_Rules/process/worktree-tasks.md#6-integration-and-cleanup)；仅当当前消息写明只清理 Orca 时才留分支。
