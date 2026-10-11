---
name: bevy-tilemap
description: "Docs-first stub for Bevy tile maps. Godot counterpart: godot-tilemap-mastery. Keywords: Bevy, tilemap, tiles, gaps, ECS, Sprite."
---

# Bevy tilemap (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-tilemap-mastery.

## When to use

Load this before storing a grid of tiles. The opened crate has sprites and meshes, not a tilemap module.

## ECS shape

- **Components:** a cell can be your own component (grid coord plus an id) spawned through normal ECS. `Sprite` can draw one cell. That is not a tilemap type.
- **Resources:** a map resource can hold width, height, and a seed. See bevy-data-resources.
- **Systems:** paint and collision generation are yours. No engine tile system was named.
- **Schedule:** generation on `Startup` or a state enter. Streaming was not opened.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| TileSet atlas | No atlas type on the sprite page. Gap. |
| TileMap layer | A set of entities or a resource grid. No TileMap component. |
| Autotile | Your rule table. Unverified as an engine feature. |

## Gaps

- No tilemap feature appears in the 0.20.0 feature list that was opened.
- No tilemap module appears in the module list.
- No third-party tile crate was chosen.

## NEVER

- No Godot TileMap or TileSet types.
- No named tilemap crate as the chosen solution.

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
- [bevy::sprite](https://docs.rs/bevy/latest/bevy/sprite/index.html) - `Sprite` only. Not a tile map.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-procedural-generation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-procedural-generation/SKILL.md) - Seeded layouts.
- [bevy-data-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-data-resources/SKILL.md) - Map resource.

#### Complements
- [godot-tilemap-mastery](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-tilemap-mastery/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
