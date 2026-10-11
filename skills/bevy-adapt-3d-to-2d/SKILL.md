---
name: bevy-adapt-3d-to-2d
description: "Docs-first stub for moving a Bevy game from 3D to 2D. Godot counterpart: godot-adapt-3d-to-2d. Keywords: Bevy, 3D, 2D, adapt, sprite, camera."
---

# Bevy adapt 3D to 2D (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-adapt-3d-to-2d.

## When to use

Load this when a 3D design should render as sprites or billboards. Gameplay components stay. Render components change.

## ECS shape

- **Draw:** replace mesh and PBR material entities' render parts with `Sprite` where a billboard is enough.
- **Camera:** use `Camera2d` from bevy-camera-systems.
- **Lights:** 3D light entities are not required for an unlit sprite. Do not leave clustered-light assumptions in gameplay code.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Mesh actor | Sprite plus the same gameplay components. |
| Perspective camera | Camera2d. |
| Height | A sort value you store. No 2.5D engine mode was opened. |

## Gaps

- Billboard and impostor types were not opened.
- Physics dimension change waits on the solver gap.

## NEVER

- No Godot convert-to-2D operations.

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

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-camera-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-camera-systems/SKILL.md) - Camera2d.
- [bevy-2d-animation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-2d-animation/SKILL.md) - Sprite clips.

#### Complements
- [bevy-adapt-2d-to-3d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-adapt-2d-to-3d/SKILL.md) - The reverse adapt.
- [godot-adapt-3d-to-2d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-adapt-3d-to-2d/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
