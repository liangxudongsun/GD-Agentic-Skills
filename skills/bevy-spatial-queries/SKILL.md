---
name: bevy-spatial-queries
description: "Docs-first stub for Bevy spatial queries. Godot counterpart: godot-raycasting-queries. Not a full port. Keywords: Bevy, raycast, shapecast, picking, physics query, gaps."
---

# Bevy spatial queries (docs-first stub)

Not a full port. Casts, overlaps, and physics picking wait on a solver. No crate was chosen.

## When to use

Load this when a design needs line of sight, a volume overlap, a ground probe, or a mouse pick, and you need the gap list. Screen-to-2D-world mapping that does not hit a collider is a camera helper, not a physics query.

## ECS shape

- **Components** would own query origin, direction, and a mask once a solver defines them. This pass does not name those types.
- **Resources** would own a physics world. None was opened.
- **Systems** would run the query after the solver step. Order that with `.chain()` on the ECS page. The clock is `Fixed` / `FixedMain` from `bevy::time`, which is not a query API.
- **Camera-only pick (opened elsewhere):** `Camera::viewport_to_world_2d` with `GlobalTransform` maps a viewport position to a 2D world position. That is not an intersection test. See bevy-camera-systems.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Ray or shape cast | Unverified until a solver page is opened. Route the gap to bevy-physics-2d or bevy-physics-3d |
| Mouse position in 2D world | `viewport_to_world_2d` on a `Camera` (bevy-camera-systems). Collider hit is still a gap |
| Exclude the caster | Unverified. Do not copy Godot RID exclude lists |
| Field-of-view fan | Design data on components. No sensor API was opened |

## Gaps

- The opened `bevy` 0.20.0 feature list has no physics-engine feature, so there is no ray, shape, point, or sweep query to cite.
- Third-party plugins may be added with `add_plugins`. This pass did not open a query API on any physics crate.
- Piercing casts, reflection from normals, and ground volumes are unverified.

## NEVER

- No Godot ray, shape-cast, or direct-space-state types.
- No Avian, Rapier, or any other named physics crate as the chosen solver.
- No invented `intersect_ray` or mask APIs.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/) - Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/) - Unversioned API index. No spatial-query module was opened.
- [Assets](https://bevy.org/assets/) - Official asset catalog. No query plugin was selected.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples) - Example tree on the `latest` branch.
- [ECS](https://bevy.org/learn/quick-start/getting-started/ecs/) - Systems, `Query`, and `.chain()`.
- [bevy::camera](https://docs.rs/bevy/latest/bevy/camera/index.html) - `viewport_to_world_2d` is a camera map, not a collider query. Details live on bevy-camera-systems.
- [Quick Start: plugins](https://bevy.org/learn/quick-start/getting-started/plugins/) - Third-party `add_plugins` without a chosen crate.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - ECS ownership.
- [bevy-camera-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-camera-systems/SKILL.md) - Viewport to 2D world, without a hit test.

#### Complements
- [bevy-physics-2d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-physics-2d/SKILL.md) - 2D solver gap.
- [bevy-physics-3d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-physics-3d/SKILL.md) - 3D solver gap.
- [godot-raycasting-queries](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-raycasting-queries/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- [bevy-ai-navigation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ai-navigation/SKILL.md) - Sensors stay a gap until queries exist.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
