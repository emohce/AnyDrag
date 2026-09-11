# AnyDrag Architecture Map

Tool: grok
Date: 2026-09-11

## Sync Rule

Update this file when a maintained module's entrypoint, storage/data contract, integration boundary, key workflow, or verification command changes. Keep entries as module + technology + code address. Do not copy the official contributor guide.

## Request Path

```text
NSApplication (main.swift)
  └─ AppDelegate
      ├─ PermissionManager (Accessibility)
      ├─ Analytics (Aptabase, optional)
      ├─ UpdateController (Sparkle)
      ├─ MenuBarController
      └─ DragEngine (CGEventTap thread)
          ├─ TitleBarDragStrategy   # 改写坐标 → Window Server 原生拖动
          ├─ ResizeStrategy         # 最近角缩放
          ├─ TilingPanel            # 修饰键+右键
          └─ SettingsStore ← Preferences (UserDefaults)
```

## Module Index

| Module | Technology / Mechanism | Code Address | Current Notes | Last Verified |
| --- | --- | --- | --- | --- |
| App entry | AppKit | [../../AnyDrag/Sources/main.swift](../../AnyDrag/Sources/main.swift#L1) | 手写 `NSApplication`，无 `@main` | 2026-09-11 |
| Lifecycle | AppKit | [../../AnyDrag/Sources/AppDelegate.swift](../../AnyDrag/Sources/AppDelegate.swift#L4) | accessory 策略 | 2026-09-11 |
| Event tap | CoreGraphics | [../../AnyDrag/Sources/DragEngine.swift](../../AnyDrag/Sources/DragEngine.swift#L175) | 高优先级线程拦截修饰键期间的鼠标事件 | 2026-09-11 |
| Native drag | Window Server | [../../AnyDrag/Sources/DragStrategy.swift](../../AnyDrag/Sources/DragStrategy.swift#L23) | `TitleBarDragStrategy` | 2026-09-11 |
| Resize | AppKit | [../../AnyDrag/Sources/ResizeStrategy.swift](../../AnyDrag/Sources/ResizeStrategy.swift#L86) | 最近角 | 2026-09-11 |
| Tiling panel | NSPanel + SwiftUI | [../../AnyDrag/Sources/TilingPanel.swift](../../AnyDrag/Sources/TilingPanel.swift#L40) | 修饰键+右键 | 2026-09-11 |
| Permissions | Accessibility | [../../AnyDrag/Sources/PermissionManager.swift](../../AnyDrag/Sources/PermissionManager.swift#L4) | `AXIsProcessTrusted` | 2026-09-11 |
| Menu bar | NSStatusItem | [../../AnyDrag/Sources/MenuBarController.swift](../../AnyDrag/Sources/MenuBarController.swift#L3) | 开关与设置入口 | 2026-09-11 |
| Settings store | SwiftUI ObservableObject | [../../AnyDrag/Sources/Settings/PreferencesWindowController.swift](../../AnyDrag/Sources/Settings/PreferencesWindowController.swift#L26) | 桥到 `DragEngine` + `Preferences` + `Analytics` | 2026-09-11 |
| Settings window | NSWindowDelegate | [../../AnyDrag/Sources/Settings/PreferencesWindowController.swift](../../AnyDrag/Sources/Settings/PreferencesWindowController.swift#L494) | 托管 SwiftUI root | 2026-09-11 |
| Preferences | UserDefaults | [../../AnyDrag/Sources/Preferences.swift](../../AnyDrag/Sources/Preferences.swift#L24) | 排除应用、标题栏偏移、修饰键 | 2026-09-11 |
| Updates | Sparkle | [../../AnyDrag/Sources/UpdateController.swift](../../AnyDrag/Sources/UpdateController.swift#L16) | 自动更新 | 2026-09-11 |
| XcodeGen | YAML | [../../project.yml](../../project.yml#L1) | bundle `me.xueshi.anydrag`，CalVer `26.09.114` | 2026-09-11 |

## Data Contract

- 偏好存在 UserDefaults，由 `Preferences` 读写。不要另造配置文件。
- Accessibility 权限是运行时门禁；没有它引擎不会真正接管拖动。
- Sparkle / Aptabase 密钥与 Apple 签名材料不进仓库、不进任务文档。
- 生成物 `AnyDrag.xcodeproj`、`DerivedData/`、`build/` 不手改。

## Unproven

- `xcodegen generate`、Xcode Cmd+R、Accessibility 真机手势、Sparkle 更新、CI 公证均未在 2026-09-11 规则初始化任务中执行。
