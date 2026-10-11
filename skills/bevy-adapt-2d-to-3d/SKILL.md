---
name: bevy-adapt-2d-to-3d
description: "Docs-first stub for moving a Bevy game from 2D to 3D. Godot counterpart: godot-adapt-2d-to-3d. Keywords: Bevy, 2D, 3D, adapt, camera, sprite."
---

# Bevy adapt 2D to 3D (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-adapt-2d-to-3d.

## When to use

Load this when a 2D design should gain a 3D camera and meshes. Keep gameplay components. Swap render and motion representations.

## ECS shape

- **Cameras:** `Camera2d` and `Camera3d` are already documented on bevy-camera-systems. An entity should not keep both as if they were one camera mode unless that skill says so.
- **Draw:** `Sprite` is 2D. Meshes and `StandardMaterial` are 3D (bevy-3d-materials).
- **Features:** the crate page separates `2d` and `3d` profiles. Enabling 3D does not delete 2D types.
- **Motion:** bevy-character-movement stays the locomotion skill. A 3D velocity is still your component until a solver exists.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Sprite actor | A mesh entity plus the same gameplay components. |
| 2D camera | Camera3d via bevy-camera-systems. |
| Tile world | No tilemap type. See bevy-tilemap and bevy-3d-world-building. |

## Gaps

- A conversion helper that rewrites entities from 2D to 3D was not opened.
- Physics solver choice is still open on both physics skills.

## NEVER

- No Godot node convert-to-3D operations.

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
- [bevy-camera-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-camera-systems/SKILL.md) - Camera2d and Camera3d.
- [bevy-3d-world-building](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-3d-world-building/SKILL.md) - Level assembly.

#### Complements
- [bevy-adapt-3d-to-2d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-adapt-3d-to-2d/SKILL.md) - The reverse adapt.
- [godot-adapt-2d-to-3d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-adapt-2d-to-3d/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
