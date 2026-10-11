---
name: bevy-animation-graph
description: "Docs-first stub for Bevy animation blending. Godot counterpart: godot-animation-tree-mastery. Keywords: Bevy, AnimationGraph, blend, AnimationGraphHandle, AnimationNodeType."
---

# Bevy animation graph (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-animation-tree-mastery.

## When to use

Load this when clips must blend, add, or mask. Single-clip playback stays on bevy-animation.

## ECS shape

- **Assets:** `AnimationGraph` describes how clips blend. `AnimationGraphNode` is one node. `AnimationNodeType` covers clip, blend, or add.
- **Components:** `AnimationGraphHandle` is a handle to the graph used by the `AnimationPlayer` on the same entity.
- **Masks:** `AnimationMask` is a bitfield alias on the graph page. Bit layout was not opened.
- **Systems:** evaluation still runs through the animation player systems. Do not add a second player.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Blend tree | AnimationGraph plus AnimationGraphHandle |
| State machine tree | Not the same type. App or entity states stay on bevy-state-machines. |
| Additive layer | AnimationNodeType includes add. Weights were not opened. |

## Gaps

- Transition APIs live under `bevy::animation::transition` and were not opened.
- Graph load and save error enums exist. File format steps were not opened.
- A 1D or 2D blend-space type was not on the graph page.

## NEVER

- No Godot AnimationTree, BlendSpace, or state-machine node types.

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
- [animation graph](https://docs.rs/bevy/latest/bevy/animation/graph/index.html) - `AnimationGraph`, `AnimationGraphHandle`, `AnimationNodeType`.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-animation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-animation/SKILL.md) - Player and clips the graph drives.

#### Complements
- [bevy-state-machines](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-state-machines/SKILL.md) - Gameplay mode is not an animation graph.
- [godot-animation-tree-mastery](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-animation-tree-mastery/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
