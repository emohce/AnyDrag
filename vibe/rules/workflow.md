# Workflow Rules

Tool: tool-neutral (codex, claude, grok, and any CodeNote-routed agent)

## Commands

Prefer documented project scripts over inventing new ones. Do not run notarize、Sparkle 发布、Homebrew tap、`bump-version.sh --push` or tag `v*` unless the current task explicitly authorizes them.

```bash
brew install xcodegen          # 一次性工具
xcodegen generate              # 从 project.yml 生成 AnyDrag.xcodeproj
open AnyDrag.xcodeproj         # 然后 Cmd+R
scripts/bump-version.sh        # 只 bump CalVer；默认不 push
```

安装现成发布包走上游 Homebrew cask 或 GitHub Releases `.dmg`，不要把安装当成源码构建成功。

源码构建需要完整 Xcode 16+ 和 macOS 13+。`project.yml` 改完必须重新 `xcodegen generate`。

## Verification

- Rule-only edits: run the CodeNote project audit below. Do not generate the Xcode project、启动 App 或公证只为证明文档。
- Code changes: regenerate the Xcode project if `project.yml` changed, then run the focused scheme build that covers the touched Swift files.
- Do not claim Accessibility 真机手势、Sparkle 更新、CI 公证或 Homebrew 发布已通过 without runtime evidence.
- For documentation-heavy changes, validate Markdown links and record unresolved links.

## Required AI Rule Audit

From the repository root, using the CodeNote audit relative to this clone:

```bash
python3 ../../CzzProj/CodeNote/AiRef/VibePractice/Vibe_Rules/scripts/audit_ai_rules.py . --mode project --fix-links
python3 ../../CzzProj/CodeNote/AiRef/VibePractice/Vibe_Rules/scripts/audit_ai_rules.py . --mode project
```
