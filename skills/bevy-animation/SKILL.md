---
name: bevy-animation
description: "Docs-first stub for Bevy animation playback. Godot counterpart: godot-animation-player. Keywords: Bevy, AnimationPlayer, AnimationClip, AnimationPlugin, animate_targets."
---

# Bevy animation playback (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-animation-player.

## When to use

Load this when an entity should play an AnimationClip. Blend graphs belong on bevy-animation-graph. 2D sprite specifics belong on bevy-2d-animation.

## ECS shape

- **Components:** `AnimationPlayer` controls playback. `AnimatedBy` links a target entity to the player entity. `AnimationTargetId` selects which curves apply.
- **Assets:** `AnimationClip` holds `VariableCurve` entries.
- **Systems:** `advance_animations` advances time. `animate_targets` writes the curves. `AnimationPlugin` adds animation support.
- **Events:** `AnimationEvent` can be triggered from a clip. Observer wiring was not opened beyond the trait name.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Timeline player | AnimationPlayer on an entity, not a node |
| Clip asset | AnimationClip |
| Which bone or field | AnimationTargetId plus AnimatedBy |
| Repeat | RepeatAnimation |

## Gaps

- Method names on AnimationPlayer (play, pause, seek) were not opened. Do not invent them.
- glTF curve loading is a separate module (`gltf_curves`) and the `gltf_animation` feature. Loader steps were not opened.
- Root motion extraction was not opened.

## NEVER

- No Godot AnimationPlayer node or track types.

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
- [bevy::animation](https://docs.rs/bevy/latest/bevy/animation/index.html) - Player, clip, plugin, advance and animate systems.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.

#### Complements
- [bevy-animation-graph](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-animation-graph/SKILL.md) - Blend instead of a single clip.
- [bevy-2d-animation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-2d-animation/SKILL.md) - Sprite targets.
- [bevy-asset-scenes](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-asset-scenes/SKILL.md) - Load clip assets.
- [godot-animation-player](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-animation-player/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- [bevy-animation-graph](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-animation-graph/SKILL.md) - Consumes clips.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
