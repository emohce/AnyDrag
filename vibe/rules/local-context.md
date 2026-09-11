<!-- codenote-local-context:conditional-v3 -->
# Project context

Project-owned conditional detail. Edit this local owner for project-specific facts; global policy stays in the compact core. Commands and inline paths are relative to the repository root unless their original text says otherwise. Read the sections relevant to the affected surface before material work.

本仓库是 `CzzRef/AnyDrag` 的本机 GitFork 检出，上游为 `XueshiQiao/AnyDrag`。本地开发主分支是 `czz-dev`。不要复述 CodeNote 规则正文。

- 过程枢纽：[vibe/specs/PROJECT_STATUS.md](<../specs/PROJECT_STATUS.md>)
- 项目规则：[README.md](<README.md>)
- 架构地图：[../knowledge/architecture.md](<../knowledge/architecture.md>)

硬边界：不要建空的 `vibe/ai-db/` 或 `vibe/requirements/`；上游 PR 不要带 `vibe/`；未授权不要 `xcodegen` 以外的公证、Sparkle 发布、Homebrew tap 或 `bump-version.sh --push`。用户给出的 `emohce/AnyDrag` 当时与上游 `main` 完全一致，GitFork origin 使用 `CzzRef/AnyDrag`。

## Project context from AGENTS.md

# AnyDrag

macOS menu bar utility that lets you move any window by holding a modifier key and dragging anywhere on it -- bypasses Accessibility API lag by simulating a native title bar drag at the window server level.

## Tech Stack
- Swift 5.9, macOS 13.0+. AppKit core (engine, menu bar, overlays); the Settings window is SwiftUI hosted in an `NSHostingController`.
- XcodeGen (`project.yml`) generates the Xcode project
- Localized: English, Simplified Chinese (via `Localizable.strings` + `LocalizationOverride`; SwiftUI reads them through the `L(_:)` helper)

## Architecture
- `main.swift` -- manual NSApplication setup (no storyboards, no @main)
- `DragEngine` -- CGEvent tap on a dedicated high-priority thread intercepts mouse events when modifier held
- `TitleBarDragStrategy` -- rewrites mouse coordinates to title bar region so the window server handles the drag natively (zero per-frame IPC)
- `MenuBarController` -- NSStatusItem menu bar UI
- `TilingPanel` -- right-click tiling overlay (halves, quarters, fill)
- `PermissionManager` -- Accessibility permission prompt
- Settings (`Sources/Settings/`) -- a SwiftUI `NavigationSplitView` with a native System-Settings-style sidebar, aligned with the sibling app HyperCapslock. `PreferencesWindowController` hosts `SettingsRootView`; `SettingsStore` is the one ObservableObject bridging SwiftUI bindings to the live `DragEngine` + `Preferences` (UserDefaults) + `Analytics`. Pages: Window Drag / Window Resize / Middle Click / Excluded Apps / General / About.

## Build
```bash
brew install xcodegen
xcodegen generate
open AnyDrag.xcodeproj  # then Cmd+R
```
