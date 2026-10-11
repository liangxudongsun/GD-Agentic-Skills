---
name: bevy-tweening
description: "Docs-first stub for Bevy tween and juice. Godot counterpart: godot-tweening. Keywords: Bevy, tween, juice, curve, gaps, ECS."
---

# Bevy tweening (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-tweening.

## When to use

Load this when a value should ease over time. The opened pages do not include a tween player.

## ECS shape

- **Feature:** `bevy_curve` is described as mathematical curves, not a tween player.
- **Components:** a tween would be your own start, end, and elapsed fields until a player type is opened.
- **Systems:** step elapsed time on `Update` or the fixed clock (`Fixed` on bevy::time, already used by movement stubs).
- **Animation:** property animation over a clip is `AnimationClip` on bevy-animation. That is a clip, not a one-shot UI tween.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Property tween | Either your elapsed component or an AnimationClip. No Tween type was opened. |
| Sequence | Chain systems or clip order. No sequence asset was opened. |
| Callback on finish | An AnimationEvent exists for clips. A tween callback type was not opened. |

## Gaps

- `bevy::curve` module body was not opened. Do not name curve sample methods.
- No tween crate was chosen.

## NEVER

- No Godot Tween node.
- No named tween crate as the chosen solution.

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
- [bevy::curve](https://docs.rs/bevy/latest/bevy/curve/index.html) - Module exists. Described as the Curve trait. Body not opened.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-animation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-animation/SKILL.md) - Clip-based property animation.
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Fixed clock name.

#### Complements
- [godot-tweening](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-tweening/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
