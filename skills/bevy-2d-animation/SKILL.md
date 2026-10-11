---
name: bevy-2d-animation
description: "Docs-first stub for Bevy 2D sprite animation. Godot counterpart: godot-2d-animation. Keywords: Bevy, sprite, animation, AnimationPlayer, AnimationClip, 2D."
---

# Bevy 2D animation (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-2d-animation.

## When to use

Load this when a 2D actor needs clip playback on a sprite entity. Pair with bevy-animation for the player and clip types. Pair with bevy-animation-graph when clips must blend.

## ECS shape

- **Components:** `Sprite` (bevy::sprite) on the visible entity. `AnimationPlayer` and `AnimationTargetId` / `AnimatedBy` (bevy::animation) link a clip to that entity.
- **Resources:** clip assets are `AnimationClip` handles, not a global player.
- **Systems:** `advance_animations` and `animate_targets` are the engine systems named on the animation page. Gameplay code should not reimplement them.
- **Schedule:** those systems are engine-owned. Gameplay that reacts to a finished clip chains after them.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Sprite frames | Sprite plus an AnimationClip. Atlas layout was not a struct on the sprite page. |
| Cutout bones | AnimationTargetId identifies which curves hit which entity. A 2D cutout rig was not opened. |
| Looping | RepeatAnimation is the repetition enum on the animation page. |

## Gaps

- The sprite page lists `Sprite`, `SpritePlugin`, `Anchor`, and `Text2d`. It does not list a texture-atlas or sprite-frames type. Do not invent one.
- `animated_field` exists as a macro on the animation page. This pass did not open its argument rules.
- Skeletal 2D cutout weights are unverified.

## NEVER

- No Godot AnimatedSprite or sprite-frames types.

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
- [bevy::sprite](https://docs.rs/bevy/latest/bevy/sprite/index.html) - `Sprite`, `SpritePlugin`.
- [bevy::animation](https://docs.rs/bevy/latest/bevy/animation/index.html) - `AnimationPlayer`, `AnimationClip`, `animated_field`.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-animation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-animation/SKILL.md) - AnimationPlayer and AnimationClip.

#### Complements
- [bevy-animation-graph](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-animation-graph/SKILL.md) - Blend clips.
- [godot-2d-animation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-2d-animation/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
