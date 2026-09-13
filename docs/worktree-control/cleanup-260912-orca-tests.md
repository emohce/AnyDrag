# 已清理的 Orca 测试工作树

当前权威：本记录只保存已拆除测试树的收口证据；活树观察在 [WORKTREE_TASKS.md](../../WORKTREE_TASKS.md) 与 [index.json](index.json)。

清理原因：用户确认这些树是 Orca 探测残留，相对 `origin/main` 无独有提交、无远端同名分支、无任务卡或需求文档。Orca `worktree rm` 已去掉展示卡、检出目录和本地分支；本文件补仓库文档归档，避免只清 UI。

| 显示名 | 本地分支 | 基线 | Git 结论 | 拆除 |
| --- | --- | --- | --- | --- |
| porbeagle | `a222757/porbeagle` | `origin/main` `9eb03c93` | 干净、无独有提交 | 已拆除；目录与分支不存在 |
| 260912-yin-yang-probe | `a222757/260912-yin-yang-probe` | `origin/main` `9eb03c93` | 干净、无独有提交；曾挂在 `czz-dev` 下 | 已拆除；父树 `childWorktreeIds` 已空 |
| a222757/给我测试一下这个Orca本身重命名的能力 | `a222757/给我测试一下这个Orca本身重命名的能力` | `origin/main` `9eb03c93` | 干净、无独有提交、无活终端 | 已拆除；目录与分支不存在 |

物理迁移：不迁移。这些树从未写入 `vibe/specs/` 任务卡，没有可逻辑归档的旧正文；替代入口即本记录与本次 [task-card](../../vibe/specs/2609/260913/1005-orca-test-worktree-cleanup/task-card.md)。

不恢复：不要按原路径重建。若需再测 Orca 父子 lineage，另开新探测树并在拆除后回写本索引。

后续默认：用户说清理时同时拆 Orca 卡、Git worktree 和本地分支，并回写本索引；只有当前消息明确「只清理 Orca」才留 Git 引用。策略在 CodeNote [worktree-tasks §6](../../../../CzzProj/CodeNote/AiRef/VibePractice/Vibe_Rules/process/worktree-tasks.md#6-integration-and-cleanup)。

2026-09-13 真实路径再核：三棵树相对 `origin/main` 无独有提交，无需合并。`git worktree list` / `git branch --list` 无对应项；`git worktree prune -n` 空；`/Users/gdkmjd/orca/workspaces/AnyDrag/{porbeagle,260912-yin-yang-probe,给我测试一下这个Orca本身重命名的能力}` 不存在；`.orca-worktree-trash` 为空。剩余活树 `settings-polish` 与 `grok/260912-paseo-probe` 仍可列出，未纳入本轮拆除。
