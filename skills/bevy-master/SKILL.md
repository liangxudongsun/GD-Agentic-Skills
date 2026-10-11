---
name: bevy-master
description: "Bevy ECS hub for this library. Orchestrates Bevy domain skills as they appear. Use when starting a Bevy game, choosing ECS boundaries, or routing to a Bevy skill. Phase-1 hub; the parity matrix is the routing table. Keywords: Bevy, ECS, bevy-master."
---

# Bevy Master: ECS hub

Phase-1 hub. Peer of the Godot hub, not a parent of it. The living matrix is the routing table. This file does not claim a port of the Godot library.

## Library target

Bevy stable pinned in this file's Reference on the implement date: **0.20.0** (crates.io, 2026-10-08; docs.rs `bevy` 0.20.0). Version hops do not live in this hub.

## Who owns what (ECS)

For every piece of state, name:

- which **component** or **resource** owns it
- which **system** may mutate it
- which message or observer should observe it

Schedules replace a scene tree. Do not add an autoload, a signal bus, or a Node layer cake.

The Quick Start ECS page (opened 2026-10-11) defines entities, components (`Component`), systems as functions, `Query`, `Commands`, `Startup`, and `Update`, plus `.chain()` for order. Messages, observers, resources, and app states are opened in the Batch B skills. See those files before calling a type.

## Decision matrix

| Scenario | Route |
| --- | --- |
| New Bevy app, ECS boundaries, which skill to load | This hub, then the matrix |
| New crate, Cargo features, feature folders | [bevy-project-foundations](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-project-foundations/SKILL.md) |
| Entity composition, components, systems | [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) |
| Messages, events, observers | [bevy-events-messaging](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-events-messaging/SKILL.md) |
| Components and resources as data | [bevy-data-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-data-resources/SKILL.md) |
| App states or a per-entity mode flag | [bevy-state-machines](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-state-machines/SKILL.md) |
| App-wide resources and schedules | [bevy-app-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-app-resources/SKILL.md) |
| Character movement | [bevy-character-movement](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-character-movement/SKILL.md) |
| 3D physics | [bevy-physics-3d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-physics-3d/SKILL.md) |
| Keyboard, mouse, gamepad | [bevy-input-handling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-input-handling/SKILL.md) |
| 2D or 3D camera entity | [bevy-camera-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-camera-systems/SKILL.md) |
| Play or control a clip | [bevy-audio-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-audio-systems/SKILL.md) |
| Load assets or spawn a scene | [bevy-asset-scenes](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-asset-scenes/SKILL.md) |
| Player save slot | [bevy-save-load](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-save-load/SKILL.md) (gap: no save format opened) |
| Logs and frame diagnostics | [bevy-debugging-profiling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-debugging-profiling/SKILL.md) |
| Parallelism, fixed step, handle lifetime | [bevy-performance](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-performance/SKILL.md) |
| `cargo test` | [bevy-testing-patterns](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-testing-patterns/SKILL.md) |
| Godot language, version hops, CLI, or project audit | Stay on the Godot skill (`n_a_godot_only` in the matrix) |
| Networking or a dedicated server | Blocked until 2026-11-11. No Bevy skill |
| Any other genre or domain | No Bevy skill yet. Read the matrix |

## When not to spawn an entity

Data that is not simulated can be a plain Rust struct or a resource. The Quick Start treats resources as app-wide data (resources page linked from the same guide; this pass opened plugins and ECS, not the resources page body). Do not copy a Godot Object / RefCounted / Resource / Node table into Bevy.

## Workflows

**(a) App scaffold.** `App::new()`, plugins, schedules, and states. The plugins page documents `Plugin`, `DefaultPlugins`, `MinimalPlugins`, and `add_plugins`. The `bevy` 0.20.0 crate docs list a `bevy_state` feature ("built in global state machines"). This pass did not open the state API. Do not invent a plugin list beyond `DefaultPlugins` / `MinimalPlugins`.

**(b) Entity.** Components plus systems. Movement belongs on a fixed timestep. `bevy::time` 0.20.0 documents `Fixed` ("fixed timestep game clock") and `run_fixed_main_schedule` (`FixedMain`). Do not invent a schedule label beyond those names.

**(c) Data.** Components and resources. Not `.tres` files.

**(d) Performance.** The ECS page states systems run in parallel by default when they can, and `.chain()` forces order. Frame-time diagnostics and handle lifetimes are on `bevy-performance`. No numeric budget is copied here; the opened pages do not give one.

## NEVER

- No umbrella skill over Godot and Bevy.
- No Godot or gdext type imports in Bevy code.
- No GDScript line-translate.
- No APIs that this file did not open.
- No Coil or Ouroboros UI.
- No Creation Station content.
- No deleting Godot skills.
- Do not mark any row `ported`. These stubs are `docs_mapped`.

## Module directory

Phase-1 domain stubs:

- [bevy-project-foundations](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-project-foundations/SKILL.md)
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md)
- [bevy-events-messaging](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-events-messaging/SKILL.md)
- [bevy-data-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-data-resources/SKILL.md)
- [bevy-state-machines](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-state-machines/SKILL.md)
- [bevy-app-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-app-resources/SKILL.md)
- [bevy-character-movement](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-character-movement/SKILL.md)
- [bevy-physics-3d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-physics-3d/SKILL.md)
- [bevy-input-handling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-input-handling/SKILL.md)
- [bevy-camera-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-camera-systems/SKILL.md)
- [bevy-audio-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-audio-systems/SKILL.md)
- [bevy-asset-scenes](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-asset-scenes/SKILL.md)
- [bevy-save-load](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-save-load/SKILL.md)
- [bevy-debugging-profiling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-debugging-profiling/SKILL.md)
- [bevy-performance](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-performance/SKILL.md)
- [bevy-testing-patterns](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-testing-patterns/SKILL.md)

The matrix holds the rest.

## Reference

Living matrix: [parity-matrix.md](references/parity-matrix.md) (full inventory).

docs.rs links use the unversioned `latest` permalink (same role as Godot `/en/stable/`). The library pin above stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/)  -  Unversioned hop index. Version numbers stay in prose; this link does not pin a release.
- [bevy crate](https://docs.rs/bevy/latest/bevy/)  -  Unversioned API index. Feature samples on the pinned page may still show older version strings.
- [Assets](https://bevy.org/assets/)  -  Official asset catalog.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples)  -  Example tree on the `latest` branch, not a release tag.
- [Quick Start](https://bevy.org/learn/quick-start/)  -  Guide index. The legacy `/learn/book/` path returned 404 on 2026-10-11.
- [Getting started](https://bevy.org/learn/quick-start/getting-started/)  -  App setup before ECS and plugins.
- [ECS](https://bevy.org/learn/quick-start/getting-started/ecs/)  -  Entities, components, systems, `Query`, `Commands`, `Startup`, `Update`, and `.chain()`.
- [Plugins](https://bevy.org/learn/quick-start/getting-started/plugins/)  -  `Plugin`, `DefaultPlugins`, `MinimalPlugins`, and `add_plugins`.
- [bevy::time](https://docs.rs/bevy/latest/bevy/time/index.html)  -  `Fixed` and `run_fixed_main_schedule` (`FixedMain`).
- [crates.io bevy](https://crates.io/crates/bevy)  -  Release pin source (0.20.0, 2026-10-08).

### Related Skills

#### Prerequisites
- None. This hub is the Bevy entry point.

#### Complements
- [godot-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-master/SKILL.md)  -  Peer hub for Godot. Language, version hops, CLI, and project audit stay there (`n_a_godot_only` in the matrix).

#### Downstream / consumers
- [bevy-project-foundations](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-project-foundations/SKILL.md)  -  Crate, Cargo features, and layout habits.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md)  -  Components, spawn tuples, queries, and `.chain()`.
- [bevy-events-messaging](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-events-messaging/SKILL.md)  -  `Message` readers and `Event` observers.
- [bevy-data-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-data-resources/SKILL.md)  -  `Component` versus `Resource`.
- [bevy-state-machines](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-state-machines/SKILL.md)  -  `bevy::state` and per-entity mode flags.
- [bevy-app-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-app-resources/SKILL.md)  -  App-wide resources and `Startup` / `Update`.
- [bevy-character-movement](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-character-movement/SKILL.md)  -  Player and actor motion on the fixed timestep.
- [bevy-physics-3d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-physics-3d/SKILL.md)  -  Simulated 3D bodies once a solver crate is verified.
- [bevy-input-handling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-input-handling/SKILL.md)  -  `ButtonInput`, mouse, and gamepad.
- [bevy-camera-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-camera-systems/SKILL.md)  -  `Camera2d` and `Camera3d`.
- [bevy-audio-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-audio-systems/SKILL.md)  -  `AudioPlayer` and `AudioSink`.
- [bevy-asset-scenes](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-asset-scenes/SKILL.md)  -  `AssetServer` and `spawn_scene`.
- [bevy-save-load](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-save-load/SKILL.md)  -  Save-slot gap. Scene spawn is not a save.
- [bevy-debugging-profiling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-debugging-profiling/SKILL.md)  -  `LogPlugin` and diagnostics plugins.
- [bevy-performance](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-performance/SKILL.md)  -  Parallel systems, fixed step, handle lifetimes.
- [bevy-testing-patterns](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-testing-patterns/SKILL.md)  -  `cargo test`. Not GdUnit.

#### Master
- This file. Do not route Bevy work through a parent that also owns Godot.

Cipher rule titles only: Godot is source of truth; blockers on blocked and `n_a_godot_only` rows; runtime gameplay is Rust; do not pull Godot types into Bevy crates.

## Gaps

- Resources, states, messages, and observers: opened for the Batch B skills. Call only the types those skills cite. `App` state-installation method names are still unopened.
- The getting-started snippet still shows `bevy = "0.19"` while crates.io latest is 0.20.0. Pin **0.20.0** from crates.io and docs.rs, not from that stale snippet.
- docs.rs feature examples on the 0.20.0 page still show `version = "0.18"` in one sample. That sample is not the pin.
