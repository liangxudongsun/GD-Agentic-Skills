---
name: bevy-camera-systems
description: "Docs-first stub for Bevy cameras. Godot counterpart: godot-camera-systems. Not a full port. Keywords: Bevy, Camera, Camera2d, Camera3d, Transform."
---

# Bevy camera systems (docs-first stub)

Not a full port. A camera is an entity with camera components and a `Transform`. Follow and shake are not copied from Godot.

## When to use

Load this when a view must render 2D or 3D. `bevy::camera` on docs.rs `latest` (0.20.0) and the `two_passes` example embedded there are the sources for the names below.

## ECS shape

- **Components:** `Camera` is the viewpoint (projection and render target). A `Camera` with no render graph errors at runtime. `Camera2d` enables the 2D graph and requires `Camera`, `Projection`, and `Frustum`. `Camera3d` enables the main 3D graph and requires `Camera` and `Projection`. 3D space is right-handed: X right, Y up, Z back, so forward is -Z.
- **Spawn:** the example uses `commands.spawn((Camera3d::default(), Transform::from_xyz(...).looking_at(Vec3::ZERO, Vec3::Y)))`. A second camera sets `Camera { order: 1, clear_color: ClearColorConfig::None, ..default() }` so it draws on top without clearing.
- **Query:** systems may take `(&mut Camera, &GlobalTransform)` with `With<Camera3d>`. `Camera::viewport_to_world_2d` maps a viewport position to a 2D world position for an orthographic camera along Z.
- **Schedule:** spawn on `Startup`. A follow system, if you write one, is your own `Update` system over `Transform`. This file does not name a follow component.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Current camera | An entity with `Camera2d` or `Camera3d` |
| Camera pose | `Transform` on that entity |
| Draw order / overlay | `Camera.order` and `ClearColorConfig::None` |
| Screen point to 2D world | `viewport_to_world_2d` with `GlobalTransform` |

## Gaps

- Camera follow, look-at smoothing, and screen shake were not on the opened pages. Do not invent those components.
- Custom `CameraRenderGraph` setup was named as a requirement, not opened as a recipe.
- Split-screen and render-target textures were not opened beyond the `order` field in the example.

## NEVER

- No Godot camera node types.
- No shake, spring-arm, or follow APIs this file did not open.
- No third-party camera crates.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/)  -  Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/)  -  Unversioned API index.
- [bevy::camera](https://docs.rs/bevy/latest/bevy/camera/index.html)  -  `Camera`, `Camera2d`, `Camera3d`.
- [Camera](https://docs.rs/bevy/latest/bevy/camera/struct.Camera.html)  -  Viewpoint, `viewport_to_world_2d`, required render graph.
- [Camera3d](https://docs.rs/bevy/latest/bevy/camera/struct.Camera3d.html)  -  Right-handed 3D camera.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples)  -  Example tree on the `latest` branch.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Who owns which piece of state.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md)  -  Spawn tuples and systems.

#### Complements
- [bevy-input-handling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-input-handling/SKILL.md)  -  Mouse motion a camera system may read.
- [bevy-character-movement](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-character-movement/SKILL.md)  -  Actor the view may track. Tracking logic is still a gap here.
- [godot-camera-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-camera-systems/SKILL.md)  -  Godot counterpart. Source idea only.

#### Downstream / consumers
- [bevy-asset-scenes](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-asset-scenes/SKILL.md)  -  Scenes that include a camera entity.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Bevy router.
