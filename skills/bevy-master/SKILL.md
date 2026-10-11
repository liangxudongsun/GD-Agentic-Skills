---
name: bevy-master
description: "Bevy ECS hub for this library. Routes the docs-first Bevy domain skills. Use when starting a Bevy game, choosing ECS boundaries, or picking a Bevy skill. The parity matrix is the routing table. Keywords: Bevy, ECS, bevy-master, A-gate."
---

# Bevy Master: ECS hub

Docs-first hub for the Bevy library (A-gate depth, not a Phase-1 flood lock). Peer of the Godot hub, not a parent of it. The living matrix is the routing table. This file does not claim a full port of the Godot library. Networking stays blocked until 2026-11-11. XR stays revisit until 2026-11-11.

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
| 2D physics | [bevy-physics-2d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-physics-2d/SKILL.md) (gap: no solver crate) |
| Ray, overlap, or physics pick | [bevy-spatial-queries](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-spatial-queries/SKILL.md) (gap: same solver) |
| Navigation mesh or path data | [bevy-navigation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-navigation/SKILL.md) (gap: no nav module) |
| Chase, patrol, retarget | [bevy-ai-navigation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ai-navigation/SKILL.md) |
| Seeded level or loot layout | [bevy-procedural-generation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-procedural-generation/SKILL.md) |
| Keyboard, mouse, gamepad | [bevy-input-handling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-input-handling/SKILL.md) |
| 2D or 3D camera entity | [bevy-camera-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-camera-systems/SKILL.md) |
| Play or control a clip | [bevy-audio-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-audio-systems/SKILL.md) |
| Load assets or spawn a scene | [bevy-asset-scenes](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-asset-scenes/SKILL.md) |
| Player save slot | [bevy-save-load](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-save-load/SKILL.md) (gap: no save format opened) |
| Logs and frame diagnostics | [bevy-debugging-profiling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-debugging-profiling/SKILL.md) |
| Parallelism, fixed step, handle lifetime | [bevy-performance](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-performance/SKILL.md) |
| `cargo test` | [bevy-testing-patterns](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-testing-patterns/SKILL.md) |
| Clips, blend graphs, sprites, lights, materials, UI, or a genre loop | Module directory below. Gaps stay in each skill |
| Godot language, version hops, CLI, or project audit | Stay on the Godot skill (`n_a_godot_only` in the matrix) |
| Networking or a dedicated server | Blocked until 2026-11-11. No Bevy skill |
| Console certification | `n_a_godot_only`. No Bevy skill |
| XR / VR | `revisit` until 2026-11-11. No XR module was opened |

## When not to spawn an entity

Data that is not simulated can be a plain Rust struct or a resource. The Quick Start treats resources as app-wide data (resources page linked from the same guide; this pass opened plugins and ECS, not the resources page body). Do not copy a Godot Object / RefCounted / Resource / Node table into Bevy.

## Workflows

**(a) App scaffold.** `App::new()`, plugins, schedules, and states. The plugins page documents `Plugin`, `DefaultPlugins`, `MinimalPlugins`, and `add_plugins`. The `bevy` 0.20.0 crate docs list a `bevy_state` feature ("built in global state machines"). This pass did not open the state API. Do not invent a plugin list beyond `DefaultPlugins` / `MinimalPlugins`.

**(b) Entity.** Components plus systems. Movement belongs on a fixed timestep. `bevy::time` 0.20.0 documents `Fixed` ("fixed timestep game clock") and `run_fixed_main_schedule` (`FixedMain`). Do not invent a schedule label beyond those names.

**(c) Data.** Components and resources. Not `.tres` files.

**(d) Performance.** The ECS page states systems run in parallel by default when they can, and `.chain()` forces order. Frame-time diagnostics and handle lifetimes are on `bevy-performance`. No numeric budget is copied here; the opened pages do not give one.


## Expert Knowledge Delta

Library target in prose: **Bevy 0.20.0**. Lattice URLs stay unversioned.

Opened canon only: `Component`, `Resource`, `Query`, `Commands`, `Startup`, `Update`, `Fixed` / `FixedMain` (`bevy::time`), `.chain()`, `Plugin`, `DefaultPlugins`, `MinimalPlugins`. Messages and observers are an ownership slot. This file does not invent their struct APIs. Systems run in parallel unless `.chain()` orders the ones that conflict.

### Who owns state

| Piece | Owner | Who may mutate | Schedule |
| --- | --- | --- | --- |
| Data on one entity | `Component` | One system via `Query` | `Update` or `FixedMain` |
| One value for the whole app | `Resource` | One system | `Startup` to insert, then the schedule that reads it |
| Spawn | `Commands` | The spawning system | `Startup` for the initial world; later schedules for runtime spawn |
| Order that must not race | `.chain()` | The chained systems only | Same schedule |
| Plugin boundary | `Plugin` | `build` registers systems and resources | Before the app runs |

Borrow rule: two systems that both mutably query the same component must be ordered (`.chain()`) or split so only one writes. Unrelated systems stay parallel. That is the ECS page rule, not a guess at a system-set API.

### Decision

| If you need | Do this | Do not |
| --- | --- | --- |
| Per-entity data | `Component` + `Query` | A Godot node script |
| App-wide config or clock | `Resource` | Copy the value onto every entity |
| Stable simulation step | `FixedMain` and the `Fixed` clock | Tie simulation to raw frame `Update` |
| Startup spawn | `Commands` in `Startup` | Spawn from a render system |
| Cross-system notice that is not shared state | Message or observer slot in `bevy-events-messaging` | A new event type invented in this file |
| An API this skill did not open | A Gaps row | A fabricated crate (solver, navmesh module, net, XR) |

Load `references/a-gate-notes.md` for the same table plus the gap rule.

## NEVER

- Do not put `/0.20.0/` in lattice URLs. WHY: permalinks stay on `latest`. The 0.20.0 pin belongs in prose once.
- Do not mutably query the same component from two unordered systems. WHY: the schedule runs systems in parallel unless `.chain()` orders them.
- Do not invent a physics, navigation, networking, or XR crate here. WHY: those rows are gaps, blocked, or revisit.

- No umbrella skill over Godot and Bevy. WHY: a Godot port, an unopened API, or a public lie fails the docs-first bar.
- No Godot or gdext type imports in Bevy code. WHY: a Godot port, an unopened API, or a public lie fails the docs-first bar.
- No GDScript line-translate. WHY: a Godot port, an unopened API, or a public lie fails the docs-first bar.
- No APIs that this file did not open. WHY: a Godot port, an unopened API, or a public lie fails the docs-first bar.
- No Coil or Ouroboros UI. WHY: a Godot port, an unopened API, or a public lie fails the docs-first bar.
- No Creation Station content. WHY: a Godot port, an unopened API, or a public lie fails the docs-first bar.
- No deleting Godot skills. WHY: a Godot port, an unopened API, or a public lie fails the docs-first bar.
- Do not mark any row `ported`. These stubs are `docs_mapped`. WHY: a Godot port, an unopened API, or a public lie fails the docs-first bar.

## Module directory

Domain skills (docs-first):

- [bevy-project-foundations](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-project-foundations/SKILL.md)
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md)
- [bevy-events-messaging](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-events-messaging/SKILL.md)
- [bevy-data-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-data-resources/SKILL.md)
- [bevy-state-machines](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-state-machines/SKILL.md)
- [bevy-app-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-app-resources/SKILL.md)
- [bevy-character-movement](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-character-movement/SKILL.md)
- [bevy-physics-3d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-physics-3d/SKILL.md)
- [bevy-physics-2d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-physics-2d/SKILL.md)
- [bevy-spatial-queries](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-spatial-queries/SKILL.md)
- [bevy-navigation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-navigation/SKILL.md)
- [bevy-ai-navigation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ai-navigation/SKILL.md)
- [bevy-procedural-generation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-procedural-generation/SKILL.md)
- [bevy-input-handling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-input-handling/SKILL.md)
- [bevy-camera-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-camera-systems/SKILL.md)
- [bevy-audio-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-audio-systems/SKILL.md)
- [bevy-asset-scenes](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-asset-scenes/SKILL.md)
- [bevy-save-load](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-save-load/SKILL.md)
- [bevy-debugging-profiling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-debugging-profiling/SKILL.md)
- [bevy-performance](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-performance/SKILL.md)
- [bevy-testing-patterns](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-testing-patterns/SKILL.md)

Rendering and animation:

- [bevy-2d-animation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-2d-animation/SKILL.md)
- [bevy-animation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-animation/SKILL.md)
- [bevy-animation-graph](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-animation-graph/SKILL.md)
- [bevy-particles](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-particles/SKILL.md)
- [bevy-shaders](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-shaders/SKILL.md)
- [bevy-tilemap](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-tilemap/SKILL.md)
- [bevy-tweening](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-tweening/SKILL.md)
- [bevy-3d-lighting](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-3d-lighting/SKILL.md)
- [bevy-3d-materials](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-3d-materials/SKILL.md)
- [bevy-3d-world-building](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-3d-world-building/SKILL.md)

Gameplay:

- [bevy-ability-system](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ability-system/SKILL.md)
- [bevy-combat-system](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-combat-system/SKILL.md)
- [bevy-dialogue-system](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-dialogue-system/SKILL.md)
- [bevy-economy-system](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-economy-system/SKILL.md)
- [bevy-game-loop-collection](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-game-loop-collection/SKILL.md)
- [bevy-game-loop-harvest](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-game-loop-harvest/SKILL.md)
- [bevy-game-loop-time-trial](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-game-loop-time-trial/SKILL.md)
- [bevy-game-loop-waves](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-game-loop-waves/SKILL.md)
- [bevy-inventory-system](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-inventory-system/SKILL.md)
- [bevy-mechanic-revival](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-mechanic-revival/SKILL.md)
- [bevy-mechanic-secrets](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-mechanic-secrets/SKILL.md)
- [bevy-quest-system](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-quest-system/SKILL.md)
- [bevy-rpg-stats](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-rpg-stats/SKILL.md)
- [bevy-turn-system](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-turn-system/SKILL.md)

UI, platforms, adapts, templates:

- [bevy-ui-layout](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ui-layout/SKILL.md)
- [bevy-ui-text](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ui-text/SKILL.md)
- [bevy-ui-theming](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ui-theming/SKILL.md)
- [bevy-platform-desktop](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-platform-desktop/SKILL.md)
- [bevy-platform-web](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-platform-web/SKILL.md)
- [bevy-platform-mobile](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-platform-mobile/SKILL.md)
- [bevy-adapt-2d-to-3d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-adapt-2d-to-3d/SKILL.md)
- [bevy-adapt-3d-to-2d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-adapt-3d-to-2d/SKILL.md)
- [bevy-adapt-desktop-to-mobile](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-adapt-desktop-to-mobile/SKILL.md)
- [bevy-adapt-mobile-to-desktop](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-adapt-mobile-to-desktop/SKILL.md)
- [bevy-project-templates](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-project-templates/SKILL.md)

Genre routers:

- [bevy-genre-action-rpg](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-action-rpg/SKILL.md)
- [bevy-genre-fighting](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-fighting/SKILL.md)
- [bevy-genre-platformer](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-platformer/SKILL.md)
- [bevy-genre-shooter](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-shooter/SKILL.md)
- [bevy-genre-shooter-fps](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-shooter-fps/SKILL.md)
- [bevy-genre-rts](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-rts/SKILL.md)
- [bevy-genre-tower-defense](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-tower-defense/SKILL.md)
- [bevy-genre-metroidvania](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-metroidvania/SKILL.md)
- [bevy-genre-open-world](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-open-world/SKILL.md)
- [bevy-genre-roguelike](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-roguelike/SKILL.md)
- [bevy-genre-survival](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-survival/SKILL.md)
- [bevy-genre-card-game](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-card-game/SKILL.md)
- [bevy-genre-educational](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-educational/SKILL.md)
- [bevy-genre-horror](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-horror/SKILL.md)
- [bevy-genre-puzzle](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-puzzle/SKILL.md)
- [bevy-genre-visual-novel](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-visual-novel/SKILL.md)
- [bevy-genre-romance](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-romance/SKILL.md)
- [bevy-genre-idle-clicker](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-idle-clicker/SKILL.md)
- [bevy-genre-party](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-party/SKILL.md)
- [bevy-genre-racing](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-racing/SKILL.md)
- [bevy-genre-rhythm](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-rhythm/SKILL.md)
- [bevy-genre-sandbox](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-sandbox/SKILL.md)
- [bevy-genre-simulation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-simulation/SKILL.md)
- [bevy-genre-sports](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-sports/SKILL.md)
- [bevy-genre-stealth](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-genre-stealth/SKILL.md)

No file: console (`n_a_godot_only`), XR (`revisit` 2026-11-11), export packaging (`n_a_godot_only`), networking and net-heavy genres (`blocked` until 2026-11-11). The matrix is the full list.

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
- [bevy-physics-2d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-physics-2d/SKILL.md)  -  Simulated 2D bodies. Same solver gap.
- [bevy-spatial-queries](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-spatial-queries/SKILL.md)  -  Casts and overlaps. Solver still unpicked.
- [bevy-navigation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-navigation/SKILL.md)  -  Path data gap. No nav module opened.
- [bevy-ai-navigation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ai-navigation/SKILL.md)  -  Chase and patrol policy.
- [bevy-procedural-generation](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-procedural-generation/SKILL.md)  -  Seed resource and spawn. No noise API.
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
