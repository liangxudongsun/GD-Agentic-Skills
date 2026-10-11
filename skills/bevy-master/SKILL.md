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

The Quick Start ECS page (opened 2026-10-11) defines entities, components (`Component`), systems as functions, `Query`, `Commands`, `Startup`, and `Update`, plus `.chain()` for order. Message and observer type names were not opened on this pass. See Gaps.

## Decision matrix

| Scenario | Route |
| --- | --- |
| New Bevy app, ECS boundaries, which skill to load | This hub, then the matrix |
| Character movement | [bevy-character-movement](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-character-movement/SKILL.md) |
| 3D physics | [bevy-physics-3d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-physics-3d/SKILL.md) |
| Godot language, version hops, CLI, or project audit | Stay on the Godot skill (`n_a_godot_only` in the matrix) |
| Networking or a dedicated server | Blocked until 2026-11-11. No Bevy skill |
| Any other genre or domain | No Bevy skill yet. Read the matrix |

## When not to spawn an entity

Data that is not simulated can be a plain Rust struct or a resource. The Quick Start treats resources as app-wide data (resources page linked from the same guide; this pass opened plugins and ECS, not the resources page body). Do not copy a Godot Object / RefCounted / Resource / Node table into Bevy.

## Workflows

**(a) App scaffold.** `App::new()`, plugins, schedules, and states. The plugins page documents `Plugin`, `DefaultPlugins`, `MinimalPlugins`, and `add_plugins`. The `bevy` 0.20.0 crate docs list a `bevy_state` feature ("built in global state machines"). This pass did not open the state API. Do not invent a plugin list beyond `DefaultPlugins` / `MinimalPlugins`.

**(b) Entity.** Components plus systems. Movement belongs on a fixed timestep. `bevy::time` 0.20.0 documents `Fixed` ("fixed timestep game clock") and `run_fixed_main_schedule` (`FixedMain`). Do not invent a schedule label beyond those names.

**(c) Data.** Components and resources. Not `.tres` files.

**(d) Performance.** The ECS page states systems run in parallel by default when they can, and `.chain()` forces order. No numeric budget is copied here; the opened pages do not give one.

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

- [bevy-character-movement](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-character-movement/SKILL.md)
- [bevy-physics-3d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-physics-3d/SKILL.md)

The matrix holds the rest.

## Reference

- Living matrix: [parity-matrix.md](references/parity-matrix.md) (Phase-1 seed only).
- Godot hub: [godot-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-master/SKILL.md).
- Opened 2026-10-11:
  - https://bevy.org/learn/quick-start/ (index; the legacy `/learn/book/` path returned 404)
  - https://bevy.org/learn/quick-start/getting-started/
  - https://bevy.org/learn/quick-start/getting-started/ecs/
  - https://bevy.org/learn/quick-start/getting-started/plugins/
  - https://docs.rs/bevy/0.20.0/bevy/
  - https://docs.rs/bevy/0.20.0/bevy/time/index.html
  - https://crates.io/crates/bevy (0.20.0, 2026-10-08)

Cipher rule titles only: Godot is source of truth; blockers on blocked and `n_a_godot_only` rows; runtime gameplay is Rust; do not pull Godot types into Bevy crates.

## Gaps

- Resources, states, messages, and observers: named in the outline; API pages were not opened. Do not call them.
- The getting-started snippet still shows `bevy = "0.19"` while crates.io latest is 0.20.0. Pin **0.20.0** from crates.io and docs.rs, not from that stale snippet.
- docs.rs feature examples on the 0.20.0 page still show `version = "0.18"` in one sample. That sample is not the pin.
