---
name: bevy-combat-system
description: "Docs-first stub for Bevy combat. Godot counterpart: godot-combat-system. Keywords: Bevy, combat, damage, hit, health, ECS."
---

# Bevy combat system (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-combat-system.

## When to use

Load this when hits change health. Overlap tests wait on bevy-spatial-queries and the unpicked physics solver.

## ECS shape

- **Components:** health and team id that you define. No engine combat component was opened.
- **Resources:** run-wide tables live in a resource (bevy-data-resources), not an autoload.
- **Systems:** mutate those components on `Update` or the fixed timestep. Use `.chain()` when damage must land before death.
- **Messages:** one-shot facts (hit, pickup, quest advance) go through bevy-events-messaging. This file does not add a new event type name.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Health | A component with current and max. Fields are yours. |
| Hit event | A message after a confirmed hit. |
| Hurt box | Unverified until a solver defines volumes. |

## Gaps

- No health, damage, or faction type exists in the opened Bevy modules.
- Hit detection is blocked on the same solver gap as bevy-physics-2d and bevy-physics-3d.

## NEVER

- No Godot node, resource, or signal types for this mechanic.

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

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-spatial-queries](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-spatial-queries/SKILL.md) - Casts. Solver still unpicked.
- [bevy-rpg-stats](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-rpg-stats/SKILL.md) - Attack numbers.
- [bevy-data-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-data-resources/SKILL.md) - Tables and definitions.
- [bevy-events-messaging](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-events-messaging/SKILL.md) - One-shot facts.

#### Complements
- [bevy-state-machines](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-state-machines/SKILL.md) - Mode flags.
- [godot-combat-system](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-combat-system/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
