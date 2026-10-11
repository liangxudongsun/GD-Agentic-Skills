---
name: bevy-shaders
description: "Docs-first stub for Bevy shaders. Godot counterpart: godot-shaders-basics. Keywords: Bevy, shader, material, bevy_shader, bevy_material, StandardMaterial."
---

# Bevy shaders and materials (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-shaders-basics.

## When to use

Load this when a surface needs a material or a custom shader asset. 3D PBR defaults stay on bevy-3d-materials. Do not treat this as a Godot shader-language port.

## ECS shape

- **Features opened on the crate page:** `bevy_shader` (shaders through asset handles) and `bevy_material` (material abstraction).
- **PBR hook:** `StandardMaterial` is named in feature blurbs (`pbr_anisotropy_texture` and neighbors) and in the `DistanceFog` summary on the pbr page.
- **Extension:** `ExtendedMaterial` is on the pbr page as a material that extends a base material with extra shaders and data. Its type parameters were not opened.
- **Systems:** material extraction is engine-owned. Do not schedule a custom shader compiler.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Shader material | A material asset handle. Shader source language was not opened. |
| Spatial shader | Unverified. Do not copy Godot shader hints. |
| Full-screen pass | bevy_post_process is a feature. Effect types were not opened. |

## Gaps

- The `bevy::shader` and `bevy::material` module pages were not opened. Do not name a `Shader` struct or a `Material` trait method from memory.
- WGSL entry points, bind group layout, and pipeline specialization keys were not opened.

## NEVER

- No Godot shader language or hint syntax.

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
- [bevy::pbr](https://docs.rs/bevy/latest/bevy/pbr/index.html) - `ExtendedMaterial`, `DistanceFog` mentions `StandardMaterial`.
- [bevy::material](https://docs.rs/bevy/latest/bevy/material/index.html) - Module exists. Body not opened.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-3d-materials](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-3d-materials/SKILL.md) - StandardMaterial surface fields.
- [bevy-asset-scenes](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-asset-scenes/SKILL.md) - Asset handles.

#### Complements
- [bevy-3d-lighting](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-3d-lighting/SKILL.md) - Lights are not shaders.
- [godot-shaders-basics](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-shaders-basics/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
