---
name: bevy-3d-world-building
description: "Docs-first stub for Bevy 3D level assembly. Godot counterpart: godot-3d-world-building. Keywords: Bevy, level, scene, mesh, world, ECS."
---

# Bevy 3D world building (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-3d-world-building.

## When to use

Load this when placing meshes, lights, and colliders into a level. Scene spawn mechanics stay on bevy-asset-scenes. Physics bodies stay on bevy-physics-3d.

## ECS shape

- **Spawn:** entities with transforms and render components. `bevy_mesh` provides a mesh format. Mesh primitive constructors were not opened.
- **Scenes:** `bevy_scene` and `bevy_gltf` are features. Spawn details are on bevy-asset-scenes (`AssetServer`, scene spawn).
- **Lights:** place them using bevy-3d-lighting.
- **Systems:** level streaming is your state plus asset handles. No streaming type was opened.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Packed level | A scene asset spawned through bevy-asset-scenes |
| Kitbash props | Entities. No grid-map node. |
| Environment | Lights, DistanceFog, and camera. No world-environment node. |

## Gaps

- Mesh primitive helpers were not opened.
- CSG and terrain heightmap types were not in the opened module list.
- Collider authoring waits on the physics solver gap in bevy-physics-3d.

## NEVER

- No Godot CSG, GridMap, or world-environment types.

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
- [bevy::gltf](https://docs.rs/bevy/latest/bevy/gltf/index.html) - glTF asset loader module exists.
- [bevy::mesh](https://docs.rs/bevy/latest/bevy/mesh/index.html) - Module exists. Body not opened.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-asset-scenes](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-asset-scenes/SKILL.md) - Scene spawn.
- [bevy-3d-lighting](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-3d-lighting/SKILL.md) - Lights.
- [bevy-3d-materials](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-3d-materials/SKILL.md) - Surfaces.
- [bevy-camera-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-camera-systems/SKILL.md) - View.

#### Complements
- [bevy-procedural-generation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-procedural-generation/SKILL.md) - Generated layouts.
- [bevy-physics-3d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-physics-3d/SKILL.md) - Simulated props. Solver still unpicked.
- [godot-3d-world-building](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-3d-world-building/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
