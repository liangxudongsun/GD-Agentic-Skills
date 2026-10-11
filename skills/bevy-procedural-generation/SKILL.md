---
name: bevy-procedural-generation
description: "Docs-first stub for Bevy procedural generation. Godot counterpart: godot-procedural-generation. Not a full port. Keywords: Bevy, procedural, seed, dungeon, terrain, ECS, gaps."
---

# Bevy procedural generation (docs-first stub)

Not a full port. Seeded layout is your data and systems. No noise crate, tile API, or worker-pool API was opened.

## When to use

Load this when a level, loot table, or map should be reproducible from a seed, and you need the ECS shape plus the gap list. Spawning the finished layout uses `Commands` on `Startup` or a later schedule you already use. Saving the seed is a bevy-save-load concern, and that skill still has no save format.

## ECS shape

- **Components:** cell, room, or prop facts you define. The ECS page shows plain `Component` structs and `commands.spawn`.
- **Resources:** one seed and a generator state you own as a `Resource` (see bevy-data-resources). Do not invent a Bevy RNG type.
- **Systems:** fill the resource on `Startup`, then spawn entities from that data. Use `.chain()` so spawn sees the finished grid.
- **Schedule:** `Startup` for a one-shot map. A streaming map is a later system on `Update`. No background-thread API was opened, so generation in this stub stays on the main schedules.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Seeded run | A `Resource` holding a seed you define |
| Chunk or dungeon grid | Your components, spawned with `Commands` |
| Noise, BSP, walk, collapse | Algorithm names from the Godot skill are ideas only. No Bevy function was opened |
| Tile write | No tile API here. Wait for a later tile skill |
| Nav bake after generation | Gap on bevy-navigation |

## Gaps

- No noise, RNG, or constraint-solver module was opened on docs.rs `bevy` `latest`.
- Worker threads and off-main-thread spawn were not opened. Do not invent a pool type.
- The assets catalog was not used to pick a generation plugin.
- Large-grid batching and navigation rebake are unverified.

## NEVER

- No Godot noise, tile, or thread-pool types.
- No invented noise, wave-function, or chunk APIs.
- No named third-party generation crate as the chosen tool.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/) - Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/) - Unversioned API index. No procedural module was opened.
- [Assets](https://bevy.org/assets/) - Official asset catalog. No generation plugin was selected.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples) - Example tree on the `latest` branch.
- [ECS](https://bevy.org/learn/quick-start/getting-started/ecs/) - `Component`, `Commands`, `Startup`, and `.chain()`.
- [Resources](https://bevy.org/learn/quick-start/getting-started/resources/) - App-wide seed state. API limits are on bevy-data-resources.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - ECS ownership.
- [bevy-data-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-data-resources/SKILL.md) - `Resource` versus `Component`.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Spawn tuples and `.chain()`.

#### Complements
- [bevy-asset-scenes](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-asset-scenes/SKILL.md) - Spawn a scene asset. Not a generator.
- [bevy-save-load](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-save-load/SKILL.md) - Seed persistence is still a format gap.
- [bevy-navigation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-navigation/SKILL.md) - No bake after a generated map.
- [godot-procedural-generation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-procedural-generation/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
