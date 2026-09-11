# Project Rules

Tool: tool-neutral (codex, claude, grok, and any CodeNote-routed agent)

## Project Profile

- Name: `AnyDrag`
- Path: GitFork clone at `GitFork/AnyDrag`
- Origin: `origin=emohce/AnyDrag`，`upstream=XueshiQiao/AnyDrag`
- Local working branch: `czz-dev`（从 fork `main@9eb03c93` / CalVer `26.09.114` 拉出）
- License: GPL-3.0（根 `LICENSE`）。本地改造仍受 GPL 约束，不要把 `vibe/` 或私有规则送进 `upstream` PR。
- Stack: Swift 5.9 + AppKit 核心 + SwiftUI Settings；XcodeGen（`project.yml`）生成 `AnyDrag.xcodeproj`；macOS 13+
- Purpose: 按住修饰键在窗口任意位置拖动，通过把鼠标坐标改写到标题栏区域，让 Window Server 走原生拖动，而不是逐帧 Accessibility IPC
- Initialization date: 2026-09-11

用户给出的 `emohce/AnyDrag` 已是其对 `XueshiQiao/AnyDrag` 的组织 fork，且当前身份有 admin。本地检出在 `GitFork/AnyDrag`，`origin` 必须是这份仓，不要再造 `CzzRef/AnyDrag`。

## Detected Manifests

- `project.yml`（Xcode 工程唯一源；改完必须 `xcodegen generate`）
- `AnyDrag/Info.plist` / `AnyDrag/AnyDrag.entitlements`（sandbox 关闭）
- `AGENTS.md` / `CLAUDE.md`（上游贡献者说明；首次规则投影后事实保留在 `local-context.md`）
- `scripts/bump-version.sh`（CalVer `YY.MM.<build>`，默认不 push）
- `.github/workflows/build.yml`（tag `v*` 才走签名/公证/Sparkle/Homebrew）

## Runtime Layout

| Area | Path | Role |
| --- | --- | --- |
| App entry | `AnyDrag/Sources/main.swift` | 手写 `NSApplication`，无 storyboard / `@main` |
| Lifecycle | `AnyDrag/Sources/AppDelegate.swift` | accessory 策略、权限、分析、菜单栏、拖动引擎 |
| Event tap | `AnyDrag/Sources/DragEngine.swift` | 高优先级线程上的 `CGEventTap` |
| Native drag | `AnyDrag/Sources/DragStrategy.swift` | `TitleBarDragStrategy` 改写坐标到标题栏 |
| Resize | `AnyDrag/Sources/ResizeStrategy.swift` | 最近角缩放 |
| Tiling | `AnyDrag/Sources/TilingPanel.swift` | 修饰键+右键磁贴面板 |
| Permissions | `AnyDrag/Sources/PermissionManager.swift` | Accessibility |
| Settings | `AnyDrag/Sources/Settings/` | SwiftUI `NavigationSplitView` + `SettingsStore` |
| Updates | `AnyDrag/Sources/UpdateController.swift` | Sparkle |
| Analytics | `AnyDrag/Sources/Analytics.swift` | Aptabase，可关 |

Directories that do **not** exist and must not be invented: `vibe/ai-db/`, `vibe/requirements/`.

## Local Rule Policy

- Keep project-specific constraints here; move reusable cross-project rules to CodeNote.
- Do not overwrite existing user work or unrelated business files.
- Before implementation, inspect the relevant source paths and the official contributor facts in `local-context.md`.
- Product docs remain in `README.md` / `README_CN.md` / `docs/`；本文件只记录 agent-facing 边界。
- `vibe/` belongs to `czz-dev`. Do not include it in PRs to `upstream`.
- `*.xcodeproj` is generated. Do not hand-edit it; regenerate from `project.yml`.

## High-Risk Areas

- `CGEventTap` 与 Accessibility：系统级输入拦截和改写鼠标事件。未授权不要对真实登录会话做持久事件注入实验。
- CI `build.yml` 持有 Developer ID 证书、公证凭据、Sparkle EdDSA 私钥、跨仓 PAT。不要改浮动 Action tag、不要回放 secrets、不要在本机打印这些值。
- `scripts/bump-version.sh --push`、打 `v*` tag、公证、Sparkle appcast、Homebrew tap 都是发布动作，必须当轮点名。
- `project.yml` 里的 `DEVELOPMENT_TEAM` / bundle id `me.xueshi.anydrag` 属于上游。本地签名用自己的 team，不要把上游证书配置提交回去。
- Aptabase / Sparkle 密钥、`.env`、诊断日志里的绝对路径与用户名。
- 生成物：`AnyDrag.xcodeproj`、`DerivedData/`、`build/`、`.build/`。不要手改。

## Business Constraints

- 包管理/工程生成只用 `xcodegen generate`；不要发明第二套 Xcode 工程入口。
- 源码构建需要完整 Xcode（不只 Command Line Tools）。未授权不要 `open` 后 Cmd+R 之外的公证/安装覆盖。
- 上游 PR 不要带 `vibe/`。
- 改造默认留在 `czz-dev`。不要把 `czz-dev` 推到 `upstream`。
