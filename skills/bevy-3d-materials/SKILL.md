---
name: bevy-3d-materials
description: "Docs-first stub for Bevy PBR materials. Godot counterpart: godot-3d-materials. Keywords: Bevy, StandardMaterial, PBR, material, ExtendedMaterial."
---

# Bevy 3D materials (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-3d-materials.

## When to use

Load this when a mesh needs a PBR surface. Custom shader extension points are on bevy-shaders. Lighting is on bevy-3d-lighting.

## ECS shape

- **Type named in opened text:** `StandardMaterial` (feature blurbs and `DistanceFog`).
- **Extension:** `ExtendedMaterial` on the pbr page.
- **Features that mention StandardMaterial textures:** `pbr_anisotropy_texture`, `pbr_multi_layer_material_textures`, `pbr_specular_textures`, `pbr_transmission_textures`. Field names inside the struct were not opened.
- **Plugin:** `bevy_pbr` adds PBR rendering. It is part of the 3d render collection.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| PBR surface | StandardMaterial. Albedo and roughness fields were not opened. |
| Shader override | ExtendedMaterial. Type parameters were not opened. |
| Transparency | Unverified at field level. |

## Gaps

- The StandardMaterial struct page was not opened. Do not invent albedo, metallic, or roughness field names.
- Mesh attachment component names (material handles on meshes) were not opened.

## NEVER

- No Godot StandardMaterial or shader-material types.

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
- [bevy::pbr](https://docs.rs/bevy/latest/bevy/pbr/index.html) - `StandardMaterial` mentioned, `ExtendedMaterial` listed.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-shaders](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-shaders/SKILL.md) - Custom shader gap.
- [bevy-3d-lighting](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-3d-lighting/SKILL.md) - Lights that shade the material.

#### Complements
- [godot-3d-materials](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-3d-materials/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
