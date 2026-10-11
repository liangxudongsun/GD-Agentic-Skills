---
name: bevy-ecs-composition
description: "Docs-first stub for Bevy entity composition. Godot counterpart: godot-composition. Not a full port. Keywords: Bevy, ECS, Component, Query, systems."
---

# Bevy ECS composition (docs-first stub)

Not a full port. Composition here is entities, components, and systems. It is not a node tree.

## When to use

Load this when gameplay data should be split across small components and systems, instead of one type that owns everything. The Quick Start ECS page is the source for the names below.

## ECS shape

- **Components** are Rust structs that derive `Component`. The ECS page splits `Person` and `Name` so more than one kind of entity can carry a name.
- **Entities** are spawned with `Commands` in a `Startup` system. The page spawns a tuple of components: `commands.spawn((Person, Name(...)))`.
- **Systems** are functions. `Query<&Name, With<Person>>` reads names on entities that also have `Person`. `Query<&mut Name, With<Person>>` writes. Register with `add_systems`.
- **Schedule:** `Startup` runs once. `Update` runs afterward. Systems run in parallel unless you call `.chain()`. The page chains `update_people` before `greet_people` and leaves an unrelated system outside the chain.

A `Bundle` trait page was not opened. Use the tuple spawn the ECS page shows. Do not invent a bundle macro.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Has-a parts on one object | Several `Component` structs on one entity |
| Behavior script | A system function over a `Query` |
| Spawn at start | `Commands` in a `Startup` system |
| Ordered steps | `.chain()` on the systems that depend on each other |
| Parent/child scene tree | Not opened. Do not invent a hierarchy API |

## Gaps

- Parent-child hierarchy, required-component derives, and bundle helper traits were not opened.
- Change detection and system sets were not opened. Order that matters uses `.chain()` only.
- Editor composition and Control-tree apps stay on the Godot composition-apps skill (`n_a_godot_only`).

## NEVER

- No Godot node, scene, or component-script types.
- No `Bundle` API that this file did not open.
- No third-party crates.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/)  -  Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/)  -  Unversioned API index.
- [Quick Start: ECS](https://bevy.org/learn/quick-start/getting-started/ecs/)  -  `Component`, `Query`, `With`, `Commands`, `Startup`, `Update`, and `.chain()`.
- [Apps](https://bevy.org/learn/quick-start/getting-started/apps/)  -  `App` holds the `World` and the `Schedule`.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples)  -  Example tree on the `latest` branch.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Who owns which piece of state.
- [bevy-project-foundations](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-project-foundations/SKILL.md)  -  Crate and `App` shell.

#### Complements
- [bevy-data-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-data-resources/SKILL.md)  -  App-wide data that should not be a component.
- [bevy-events-messaging](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-events-messaging/SKILL.md)  -  Cross-system notices that are not a shared component.
- [godot-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-composition/SKILL.md)  -  Godot counterpart. Source idea only. Do not import Godot types.

#### Downstream / consumers
- [bevy-character-movement](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-character-movement/SKILL.md)  -  Movement components and systems on the fixed timestep.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Bevy router.
