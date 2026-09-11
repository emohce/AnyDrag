# Changes：AnyDrag AI 规则初始化

> Inventory only. 本文件只回答改了哪些文件。

## 1. 概览

| 批次 | 提交 | 文件数 | 核心说明 |
| --- | --- | --- | --- |
| CLAUDE 落实 | `d20c446` | 1 | 把上游 `CLAUDE.md` 符号链接变成与 `AGENTS.md` 同内容的普通文件 |
| 规则初始化 | `2ee37f5` | 18 | 短入口、vibe 树、过程枢纽 |

## 2. 交付物清单

| 对象 | 类型 | 核心说明 |
| --- | --- | --- |
| GitHub `CzzRef/AnyDrag` | 新增 fork | 从 `XueshiQiao/AnyDrag` 声明 fork，仅 default branch |
| `/Users/gdkmjd/work/czz/GitFork/AnyDrag/` | 新增 clone | `origin=CzzRef/AnyDrag`，`upstream=XueshiQiao/AnyDrag`，分支 `czz-dev@9eb03c93` |
| `CLAUDE.md` | 改动 | 符号链接落实为普通文件，再投影为短入口 |
| `AGENTS.md` | 改动 | 官方贡献者说明抽出后换成 CodeNote 短入口 |
| `vibe/rules/` | 新增 | 项目规则、工作流、知识、文档路由、local-context |
| `vibe/specs/` | 新增 | 过程枢纽与本任务卡片 |
| `vibe/knowledge/` | 新增 | 架构地图与空 ADR/error-memory |
| `vibe/evals/` | 新增 | 初始化核验记录 |
| CodeNote `vibe/knowledge/project-index.json` | 改动 | 登记 `anydrag` 并恢复 `routes.rules`（CodeNote `f799e408`，未推送） |
| CodeNote `vibe/knowledge/workspace-config/workspace.local.json` | 改动（ignored） | 本机绑定 `GitFork/AnyDrag` |

## 3. 逐批清单

### CLAUDE 落实 `d20c446`

| 文件 | 核心说明 |
| --- | --- |
| `CLAUDE.md` | `120000` 符号链接 → `100644` 普通文件，内容与当时 `AGENTS.md` 相同 |

### 规则初始化 `2ee37f5`

| 文件 | 核心说明 |
| --- | --- |
| `AGENTS.md` | CodeNote 短入口 |
| `CLAUDE.md` | 指向 `AGENTS.md` 的短入口 |
| `vibe/rules/README.md` | 项目规则索引 |
| `vibe/rules/local-context.md` | 抽出的上游贡献者事实 + GitFork 身份 |
| `vibe/rules/project.md` | 栈、远程、高风险边界 |
| `vibe/rules/workflow.md` | 构建命令与审计 |
| `vibe/rules/knowledge.md` | 知识路由 |
| `vibe/rules/documentation.md` | 文档路由 |
| `vibe/specs/README.md` | 过程目录约定 |
| `vibe/specs/PROJECT_STATUS.md` | 过程枢纽 |
| `vibe/specs/2609/260911/1356-ai-rules-init/task-card.md` | 本任务卡片 |
| `vibe/specs/2609/260911/1356-ai-rules-init/changes.md` | 本清单 |
| `vibe/knowledge/README.md` | 知识索引 |
| `vibe/knowledge/architecture.md` | 模块地图 |
| `vibe/knowledge/adr/README.md` | 空 ADR |
| `vibe/knowledge/error-memory/README.md` | 空错误索引 + capture 入口 |
| `vibe/evals/README.md` | eval 目录说明 |
| `vibe/evals/2026-09-11-ai-rules-init.md` | 初始化核验 |

## 4. 明确没做的（分流，不是遗漏）

| 对象 | 数量 | 核心说明 |
| --- | --- | --- |
| 应用 Swift 代码 | 0 | 本轮只做落地与规则 |
| `xcodegen generate` / Xcode 构建 | 0 | 规则初始化不需要工程生成 |
| Accessibility 真机 | 0 | 未授权 |
| push / tag / 公证 | 0 | Skill 禁止 push |
| 把 `vibe/` 送到 upstream | 0 | 本地 czz-dev 治理 |
| CodeNote 其他脏文件 | 多 | 与本任务无关，排除 |

## 5. 用户可见行为变化

| 位置 | 变化 | 核心说明 |
| --- | --- | --- |
| 产品 App | 无 | 未改运行时 |
| GitHub CzzRef | 新增公开 fork | org 下可见 AnyDrag |
