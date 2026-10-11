---
name: bevy-data-resources
description: "Docs-first stub for Bevy components and resources as data. Godot counterpart: godot-resource-data-patterns. Not a full port. Keywords: Bevy, Resource, Res, Component, data."
---

# Bevy data resources (docs-first stub)

Not a full port. Data is a `Component` or a `Resource`. There is no scene-file twin.

## When to use

Load this when you are deciding where a piece of data lives: on many entities, or once for the whole app. The Resources page and the ECS page are the source for the names below.

## ECS shape

- **Components** are for data you query across entities (`Component`, `Query`). Use them when many things carry the same kind of fields.
- **Resources** are globally unique data (`Resource`). The Resources page names elapsed time, asset collections, and renderers as examples. Access them with `Res<T>` (read) and `ResMut<T>` (write).
- **Insert.** `insert_resource` places a resource on the `App`. The page's sample derives `Resource` on `GreetTimer(Timer)` and inserts `Timer::from_seconds(2.0, TimerMode::Repeating)`.
- **Time.** `Time` is inserted by `add_plugins(DefaultPlugins)`. `time.delta()` is the elapsed time since the last update. `Timer::tick` and `just_finished` are the page's timer methods.
- **Schedule:** The sample reads `Res<Time>` and `ResMut<GreetTimer>` inside an `Update` system. Startup versus update is on the ECS page.

Asset loading APIs were not opened. "Asset collections" on the Resources page is an example of what a resource might hold, not a loader type.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Data on one gameplay thing | A `Component` |
| One copy for the whole app | A `Resource` inserted with `insert_resource` |
| Shared clock | `Time` from `DefaultPlugins`, or your own `Resource` |
| Authored data file | Not opened. Do not invent a file format or loader |

## Gaps

- Asset handles, serialization, and reflection-based loading were not opened.
- Resource initialization order across plugins was not opened beyond a single `insert_resource` call inside `Plugin::build`.
- Per-entity data files and save blobs are out of scope. See the save-load matrix row when that skill exists.

## NEVER

- No Godot resource, packed-scene, or data-file types.
- No invented asset or serialization APIs.
- No third-party crates.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/)  -  Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/)  -  Unversioned API index.
- [Resources](https://bevy.org/learn/quick-start/getting-started/resources/)  -  `Resource`, `Res`, `ResMut`, `insert_resource`, `Time`, `Timer`, `TimerMode`.
- [Quick Start: ECS](https://bevy.org/learn/quick-start/getting-started/ecs/)  -  `Component` and `Query` for per-entity data.
- [Apps](https://bevy.org/learn/quick-start/getting-started/apps/)  -  Resources as the single copy of global data in the `World`.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples)  -  Example tree on the `latest` branch.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Component versus resource ownership.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md)  -  How components are spawned and queried.

#### Complements
- [bevy-app-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-app-resources/SKILL.md)  -  Schedules and plugins around those resources.
- [godot-resource-data-patterns](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-resource-data-patterns/SKILL.md)  -  Godot counterpart. Source idea only. Do not import Godot types.

#### Downstream / consumers
- None yet. Inventory, stats, and save skills are not ported.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Bevy router.
