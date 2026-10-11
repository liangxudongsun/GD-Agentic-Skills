---
name: bevy-debugging-profiling
description: "Docs-first stub for Bevy logs and diagnostics. Godot counterpart: godot-debugging-profiling. Not a full port. Keywords: Bevy, LogPlugin, DiagnosticsPlugin, FrameTimeDiagnosticsPlugin."
---

# Bevy debugging and profiling (docs-first stub)

Not a full port. Diagnostics are plugins and a store resource. They are not a Godot profiler panel.

## When to use

Load this when a running app should print logs or record frame time, entity count, or process CPU and memory. `bevy::log::LogPlugin` and `bevy::diagnostic` on docs.rs `latest` (0.20.0) are the sources.

## ECS shape

- **Logs:** `LogPlugin` is part of `DefaultPlugins`. Override it with `DefaultPlugins.set(LogPlugin { level, filter, .. })`. The page's example uses `Level::DEBUG` and a filter string such as `wgpu=error,bevy_render=info,bevy_ecs=trace`. The same filter works as `RUST_LOG`. To bring your own collector, disable this plugin on `DefaultPlugins`.
- **Diagnostics core:** `DiagnosticsPlugin` adds the core resources. `DiagnosticsStore` holds the collection. `Diagnostic` is a timeline of `DiagnosticMeasurement` values addressed by `DiagnosticPath`. `RegisterDiagnostic` adds `register_diagnostic` on `App`.
- **Built-in plugins:** `FrameTimeDiagnosticsPlugin` adds frame time, fps, and frame count. `EntityCountDiagnosticsPlugin` adds an entity count. `SystemInformationDiagnosticsPlugin` adds `cpu_usage` and `mem_usage` percent. `LogDiagnosticsPlugin` prints diagnostics to the console. `FrameCount` / `FrameCountPlugin` count frames since start.
- **Order:** the log-diagnostics example adds these plugins after `DefaultPlugins` because they use the time plugin for timestamps.
- **Schedule:** you do not write the measurement systems yourself unless you register your own `Diagnostic`. Reading `DiagnosticsStore` from a system was not opened as a recipe.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Print debug lines | `LogPlugin` filter or `RUST_LOG` |
| FPS readout | `FrameTimeDiagnosticsPlugin` |
| How many entities | `EntityCountDiagnosticsPlugin` |
| Process CPU and memory | `SystemInformationDiagnosticsPlugin` |
| Dump those numbers | `LogDiagnosticsPlugin` |

## Gaps

- Per-system flame graphs and Tracy wiring (`enable_tracy` appears as a field fragment on the log plugin page) were not opened as a setup guide.
- A custom `Diagnostic` registration example was not opened. Names stop at `Diagnostic`, `DiagnosticPath`, and `register_diagnostic`.
- Render-app diagnostic forwarding was not opened on docs.rs (an examples page mentions it; this skill does not copy that plugin path).

## NEVER

- No Godot debugger, monitor, or profiler types.
- No Tracy or external profiler setup this file did not open.
- No third-party profiling crates.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/)  -  Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/)  -  Unversioned API index.
- [LogPlugin](https://docs.rs/bevy/latest/bevy/log/struct.LogPlugin.html)  -  Filter, level, `RUST_LOG`.
- [bevy::diagnostic](https://docs.rs/bevy/latest/bevy/diagnostic/index.html)  -  Store, frame time, entity count, system info, log plugin.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples)  -  Example tree on the `latest` branch.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Who owns which piece of state.
- [bevy-project-foundations](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-project-foundations/SKILL.md)  -  `DefaultPlugins` and `App`.

#### Complements
- [bevy-performance](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-performance/SKILL.md)  -  What the frame-time numbers are for.
- [godot-debugging-profiling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-debugging-profiling/SKILL.md)  -  Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Bevy router.
