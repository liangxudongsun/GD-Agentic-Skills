---
name: bevy-platform-desktop
description: "Docs-first stub for Bevy desktop windows. Godot counterpart: godot-platform-desktop. Keywords: Bevy, window, desktop, WindowPlugin, PrimaryWindow, winit."
---

# Bevy desktop platform (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-platform-desktop.

## When to use

Load this when configuring the desktop window, mode, or close behavior. Web and mobile constraints stay on their skills.

## ECS shape

- **Module:** `bevy::window` is a platform-agnostic window interface. `WindowPlugin` is part of `DefaultPlugins`.
- **Components:** `Window` is the defining component for window entities. `PrimaryWindow` marks the primary window.
- **Mode:** `WindowMode`, `PresentMode`, `WindowResolution`, `WindowPosition` are enums or structs on that page.
- **Backend feature:** `bevy_winit` is the winit window and input backend. `x11` and `wayland` are features.
- **Close:** `exit_on_primary_closed` and `exit_on_all_closed` are named functions. `WindowCloseRequested` is the event.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Window size | WindowResolution on the Window component. |
| Fullscreen | WindowMode. Variants were not opened. |
| Quit on close | exit_on_primary_closed. |

## Gaps

- Per-field defaults on `Window` were not opened.
- Display-server selection code was not opened. Feature names only.

## NEVER

- No Godot DisplayServer or window project-setting names.

- No Godot types in Bevy code.
- No invented APIs or unnamed third-party crates as the chosen solver.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/) - Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/) - Unversioned API index. Feature list opened for 0.20.0.
- [Assets](https://bevy.org/assets/) - Official asset catalog. No third-party crate was selected.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples) - Example tree on the `latest` branch.
- [ECS](https://bevy.org/learn/quick-start/getting-started/ecs/) - `Component`, systems, `Query`, `Startup`, `Update`, and `.chain()`.
- [Plugins](https://bevy.org/learn/quick-start/getting-started/plugins/) - `Plugin`, `DefaultPlugins`, `MinimalPlugins`, and `add_plugins`.
- [bevy::window](https://docs.rs/bevy/latest/bevy/window/index.html) - `Window`, `WindowPlugin`, `PrimaryWindow`, `WindowMode`.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.

#### Complements
- [bevy-platform-web](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-platform-web/SKILL.md) - Wasm limits.
- [bevy-input-handling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-input-handling/SKILL.md) - Pointer and keyboard.
- [godot-platform-desktop](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-platform-desktop/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
