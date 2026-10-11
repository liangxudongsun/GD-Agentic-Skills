---
name: bevy-adapt-mobile-to-desktop
description: "Docs-first stub for adapting a Bevy mobile game to desktop. Godot counterpart: godot-adapt-mobile-to-desktop. Keywords: Bevy, desktop, mouse, keyboard, adapt, window."
---

# Bevy adapt mobile to desktop (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-adapt-mobile-to-desktop.

## When to use

Load this when a touch-first game gains a window, mouse, and keyboard. Window setup is bevy-platform-desktop.

## ECS shape

- **Window:** `Window`, `WindowMode`, and `PrimaryWindow`.
- **Input:** keyboard, mouse, and gamepad features are named on the crate page and already used by bevy-input-handling.
- **Cursor:** `CursorGrabMode` and `CursorOptions` are on the window page. Grab semantics were not opened.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Touch buttons | Keyboard and mouse via bevy-input-handling. |
| Portrait layout | A wider Node tree. No orientation type was opened. |
| Cursor lock | CursorGrabMode exists. Variants were not opened. |

## Gaps

- Hint glyphs and control prompts were not opened.
- Cursor grab mode variants were not opened.

## NEVER

- No Godot device-feature tags.

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
- [bevy::window](https://docs.rs/bevy/latest/bevy/window/index.html) - `CursorGrabMode`, `WindowMode`.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-platform-desktop](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-platform-desktop/SKILL.md) - Window.
- [bevy-input-handling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-input-handling/SKILL.md) - Keyboard, mouse, gamepad.

#### Complements
- [bevy-adapt-desktop-to-mobile](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-adapt-desktop-to-mobile/SKILL.md) - The reverse adapt.
- [godot-adapt-mobile-to-desktop](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-adapt-mobile-to-desktop/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
