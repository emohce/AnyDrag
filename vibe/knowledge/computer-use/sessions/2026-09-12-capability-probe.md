---
schema: computer-use-session/v1
session_id: 2026-09-12-capability-probe
status: completed
recording_fidelity: reconstructed-partial
project: anydrag
task_ref: grok-session-01a0954c
route_id: capability-probe-candidate
host: grok-orca-macos
application: orca
surface: computer-use-capability-probe
started_at: null
ended_at: 2026-09-12T19:11:15+08:00
privacy: sanitized
---

# Computer Use 能力核验

## Preflight

- 用户目标：核验当前 Grok 会话能否使用 Computer Use。
- 专用接口不足：用户明确要求核验 Computer Use 本身；Grok 宿主无原生 Computer Use 工具，只能走 `orca computer`。
- 已应用路线/错误记忆：Computer Use exclusion gate 的 `explicit-debug-test`；观察先于动作；不打开权限设置 UI。
- 真实边界：本机 Orca 1.4.200 + `orca-computer-use-macos`；只对 Orca 自身做窗口列表和无障碍快照，不做点击/输入。
- 允许副作用：只读 `capabilities` / `permissions` / `list-apps` / `list-windows` / `get-app-state --no-screenshot`。
- 禁止副作用：打开系统权限页、点击、打字、拖拽、操作第三方应用窗口。
- 确认门禁：权限授予与设置 UI 留给用户。
- 成功断言：报告 CLI/provider 是否可用，以及观察/动作是否被 OS 权限挡住。
- 清理与保留：无截图、无点击；仅保留本脱敏记录。

## Method Events

| seq | at | method | normalized_input | pre_state | result | post_state | assertion | decision | impact | evidence_ref |
| ---: | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| gap | time-unavailable | supporting-event | `computer capabilities` / `computer permissions` 在本记录创建前已执行 | 记录尚未建立 | capabilities ok；accessibility=not-granted；screenshots=not-granted；openedSettings=false | 权限状态已知 | 预检完成 | 继续只读探测 | none | — |
| 1 | time-unavailable | `list-apps` | 无选择器 | 权限未授予，列表能力待测 | success；返回运行中应用计数，应用名未留存 | 列表通道可用 | 应用枚举可用 | 对 Orca 列窗口 | none | — |
| 2 | time-unavailable | `list-windows` | `app=com.stablyai.orca` | Orca 在运行 | success；1 个可见窗口 `title=Orca`，`id=45327` | 目标窗口已解析 | 窗口枚举可用 | 对同一应用做无障碍快照 | none | — |
| 3 | time-unavailable | `get-app-state` | `app=com.stablyai.orca; no-screenshot` | 窗口已解析，AX 未授予 | `permission_denied`：需要 Accessibility | 无树、无截图 | 观察/动作通道不可用 | 停止 UI 调用；不打开权限 UI | none | — |

## Closeout

- process/application state：未再发起 Computer Use 方法；未点击、未输入
- user-data restoration：无 UI 变更
- retained/deleted artifacts：本会话记录；无截图
- external side effects：`permissions` 探测曾 `launchedHelper=true`，未打开系统设置
- unverified assertions：授权后 `get-app-state` / 动作类方法是否成功
- project_route：not applicable（一次性能力核验，不是 AnyDrag 产品路线）
- project_error：none（OS 权限未授予是环境状态，不是新的可复用失败指纹）
- global_extraction：none
