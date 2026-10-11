---
name: bevy-3d-lighting
description: "Docs-first stub for Bevy 3D lights. Godot counterpart: godot-3d-lighting. Keywords: Bevy, lighting, directional, point, spot, bevy_light, PBR."
---

# Bevy 3D lighting (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-3d-lighting.

## When to use

Load this when a 3D scene needs lights. Materials stay on bevy-3d-materials. Shadows and GI settings beyond the module blurbs are gaps.

## ECS shape

- **Module:** `bevy::light` says it provides directional, point, and spot lights, plus light probes, atmosphere, volumetrics, and shadow configuration.
- **Feature:** `bevy_light` is described the same way on the crate feature list.
- **PBR page names:** `DirectionalLightViewEntities`, `ExtractedDirectionalLight`, `ExtractedPointLight`, `ExtractedRectLight`, `GpuClusteredLight` (point, spot, or rectangle), `DistanceFog`, `LightProbePlugin`, `ContactShadows`.
- **Systems:** light clustering and extraction are engine-owned. Gameplay only spawns light entities.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Sun | A directional light entity. Struct method list was not opened; the module states the kind exists. |
| Omni or point | A point light. Same limit. |
| Spot | A spot light. Same limit. |
| Fog | DistanceFog on the pbr page. |
| Baked GI | Irradiance volumes are a pbr module. Baking steps were not opened. |

## Gaps

- Individual light struct pages (`DirectionalLight`, `PointLight`, `SpotLight`) were not opened, so fields such as intensity or shadow cascades are not named here.
- `bevy_solari` is an experimental raytraced-lighting feature. Its API was not opened.
- Lightmap baking workflows were not opened.

## NEVER

- No Godot light node types.

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
- [bevy::light](https://docs.rs/bevy/latest/bevy/light/index.html) - Module blurb: directional, point, spot, probes, shadows.
- [bevy::pbr](https://docs.rs/bevy/latest/bevy/pbr/index.html) - Extracted lights, fog, probes, contact shadows.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-3d-materials](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-3d-materials/SKILL.md) - Lit surfaces.
- [bevy-camera-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-camera-systems/SKILL.md) - Camera the lights affect.

#### Complements
- [bevy-3d-world-building](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-3d-world-building/SKILL.md) - Place light entities in a level.
- [godot-3d-lighting](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-3d-lighting/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
