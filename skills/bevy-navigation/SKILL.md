---
name: bevy-navigation
description: "Docs-first stub for Bevy navigation. Godot counterpart: godot-navigation-pathfinding. Not a full port. Keywords: Bevy, navigation, pathfinding, ECS, gaps."
---

# Bevy navigation (docs-first stub)

Not a full port. Bevy's opened pages do not ship a navigation mesh, agent, or avoidance solver. No third-party nav crate was chosen.

## When to use

Load this when agents need a path over walkable space and you need the gap list before adding a crate. Movement of the actor after a path exists belongs on bevy-character-movement. Policy for chase, patrol, and retarget belongs on bevy-ai-navigation.

## ECS shape

- **Components** may store a goal `Transform` target and a path as your own data (a list of positions you define). The ECS page allows plain `Component` structs. It does not define a nav agent.
- **Resources** would own a map. None was opened.
- **Systems** that follow a path you already computed should move on `Fixed` / `FixedMain` (`bevy::time`) and use `.chain()` when the next waypoint must be visible before motion. Computing the path itself has no opened API.
- **Schedule:** do not invent a navigation schedule name.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Navigation agent | Unverified. No agent component was opened |
| Baked region | Unverified. Do not copy Godot bake calls |
| Avoidance | Unverified |
| Next waypoint | Your component data, then bevy-character-movement |

## Gaps

- docs.rs `bevy` `latest` (pin 0.20.0 on bevy-master) was not opened onto a navigation module. Do not invent mesh, link, layer, or cost types.
- The assets catalog was not used to select a navigation plugin. `add_plugins` allows a third-party crate later; this pass records no path.
- Runtime rebake, stuck recovery, and crowd radius are unverified.

## NEVER

- No Godot navigation agent, region, or server types.
- No named third-party navigation crate as the chosen solver.
- No invented bake, avoidance, or path-query APIs.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/) - Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/) - Unversioned API index. No navigation module was opened.
- [Assets](https://bevy.org/assets/) - Official asset catalog. No navigation plugin was selected.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples) - Example tree on the `latest` branch.
- [ECS](https://bevy.org/learn/quick-start/getting-started/ecs/) - `Component`, `Query`, `Commands`, and `.chain()`.
- [bevy::time](https://docs.rs/bevy/latest/bevy/time/index.html) - `Fixed` and `FixedMain` for motion after a path exists.
- [Quick Start: plugins](https://bevy.org/learn/quick-start/getting-started/plugins/) - `add_plugins` without a chosen nav crate.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - ECS ownership.
- [bevy-character-movement](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-character-movement/SKILL.md) - How an actor moves once a waypoint exists.

#### Complements
- [bevy-ai-navigation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ai-navigation/SKILL.md) - Chase, patrol, and retarget policy. Not the mesh.
- [godot-navigation-pathfinding](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-navigation-pathfinding/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet. Genre routers are not ported.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
