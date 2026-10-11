---
name: bevy-ai-navigation
description: "Docs-first stub for Bevy AI navigation policy. Godot counterpart: godot-ai-navigation. Not a full port. Keywords: Bevy, AI, chase, patrol, navigation, ECS, gaps."
---

# Bevy AI navigation (docs-first stub)

Not a full port. This file routes movement decisions. It does not implement a navigation mesh.

## When to use

Load this when an actor must chase, patrol, or wait, and you need to see which Bevy skill owns the next step. Path data and any future nav crate stay on bevy-navigation. Transform integration stays on bevy-character-movement. Line-of-sight sensors stay on bevy-spatial-queries until a solver exists.

## ECS shape

- **Components:** a mode flag can be an enum `Component` (see bevy-state-machines for the pattern). Goal position can be your own component. No agent, radius, or layer type was opened.
- **Resources:** a shared patrol table can be a `Resource` you define. No navigation resource was opened.
- **Systems:** read the mode and write a desired velocity or waypoint on `Update` or `Fixed`. Use `.chain()` so policy runs before movement. Do not name a Godot-style agent callback.
- **Schedule:** `Fixed` / `FixedMain` when the result feeds the movement step.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Chase vs patrol | Enum component plus a system. Not a navigation agent |
| Retarget throttle | Your timer resource or a fixed-step counter. No opened retarget API |
| Crowd / avoidance | Gap on bevy-navigation. Do not invent radii |
| Bake vs obstacle | Gap on bevy-navigation |
| Line of sight | Gap on bevy-spatial-queries |

## Gaps

- No Bevy navigation module was opened, so node-agent versus server, bake, links, and layers have no Bevy names.
- Sensors that need a cast are blocked on the same unpicked physics solver as bevy-physics-2d and bevy-physics-3d.
- Formations and stuck recovery are design notes only.

## NEVER

- No Godot navigation agent or server types.
- No named third-party navigation or physics crate.
- No invented path, bake, or avoidance APIs.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/) - Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/) - Unversioned API index. No AI navigation module was opened.
- [Assets](https://bevy.org/assets/) - Official asset catalog. No AI plugin was selected.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples) - Example tree on the `latest` branch.
- [ECS](https://bevy.org/learn/quick-start/getting-started/ecs/) - `Component`, `Resource` pairing via bevy-data-resources, systems, and `.chain()`.
- [bevy::state](https://docs.rs/bevy/latest/bevy/state/index.html) - App states are not per-entity patrol modes. Per-entity flags stay components (bevy-state-machines).

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - ECS ownership.
- [bevy-navigation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-navigation/SKILL.md) - Path and mesh gap.
- [bevy-state-machines](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-state-machines/SKILL.md) - Enum components for a mode flag.

#### Complements
- [bevy-character-movement](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-character-movement/SKILL.md) - Integrates a waypoint or velocity.
- [bevy-spatial-queries](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-spatial-queries/SKILL.md) - Sensor gap.
- [godot-ai-navigation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-ai-navigation/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
