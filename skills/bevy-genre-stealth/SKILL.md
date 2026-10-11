---
name: bevy-genre-stealth
description: "Thin Bevy genre router for Stealth. Godot counterpart: godot-genre-stealth. Keywords: Bevy, Stealth, genre, ECS, router."
---

# Bevy Stealth (thin router)

Thin genre router. Not a full port. Godot counterpart: godot-genre-stealth. Ideas only. Domain work stays on the Bevy skills below.

## When to use

Load this for vision cones you author and alert states.

## ECS shape

- **Components** hold the genre's per-entity flags as plain data. This file does not name new engine types.
- **Resources** hold run-wide counters (score, wave index, seed) via bevy-data-resources.
- **Systems** read those components on `Update` or the fixed timestep from bevy-master. Order them with `.chain()` when a later system must see the result.
- **Schedule:** gameplay mode changes go through bevy-state-machines. Do not invent a genre plugin.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Genre scene tree | Entities plus the domain skills linked below |
| Autoload director | A resource, not a singleton node |
| Signal bus for the loop | bevy-events-messaging |

## Routing

- - [bevy-ai-navigation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ai-navigation/SKILL.md) - Patrol.
- - [bevy-state-machines](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-state-machines/SKILL.md) - Alert enum on the agent.
- - [bevy-3d-lighting](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-3d-lighting/SKILL.md) - Readability of darkness.
- - [bevy-spatial-queries](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-spatial-queries/SKILL.md) - Line of sight. Solver gap.

## Gaps

- No vision-cone or noise-meter type exists in Bevy.
- Line of sight shares the spatial-query gap.

## NEVER

- No Godot types in Bevy code.
- No invented genre APIs.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.
- Do not pick a physics or net crate here.

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
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - ECS ownership and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Spawn and query shape.

#### Complements
- [godot-genre-stealth](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-genre-stealth/SKILL.md) - Godot counterpart. Source idea only.
- - [bevy-ai-navigation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ai-navigation/SKILL.md) - Patrol.
- - [bevy-state-machines](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-state-machines/SKILL.md) - Alert enum on the agent.
- - [bevy-3d-lighting](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-3d-lighting/SKILL.md) - Readability of darkness.
- - [bevy-spatial-queries](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-spatial-queries/SKILL.md) - Line of sight. Solver gap.

#### Downstream / consumers
- None. This router does not own a second implementation.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
