---
name: bevy-character-movement
description: "Docs-first stub for Bevy character movement. Godot counterpart: godot-characterbody-2d. Not a full port. Keywords: Bevy, movement, ECS, fixed timestep."
---

# Bevy character movement (docs-first stub)

Not a full port. No Rust crate in this phase.

## When to use

Load this when a Bevy app needs a player or actor that moves in discrete steps (walk, jump feel, ground check) and you need the ECS shape before any solver code exists. Coyote time and a jump buffer are design notes. They are not a node port.

## ECS shape

- **Components** own pose and intent: position, velocity, and a jump-buffer or coyote timer as data. The Quick Start ECS page shows components as Rust structs that derive `Component`.
- **Resources** own clocks and tuning shared by every mover. `bevy::time` 0.20.0 documents `Time`, `Fixed` (fixed timestep clock), and `Virtual`.
- **Systems** read intent and write velocity or position. Register them on the fixed schedule, not on a per-node physics callback.
- **Schedule:** `run_fixed_main_schedule` runs `FixedMain` from virtual time (`bevy::time` 0.20.0). Order dependent systems with `.chain()` (ECS page). Do not paste a Godot physics-process function.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Body that you move yourself | Entity with movement components and a system |
| Step that should stay stable when frame time changes | System on the fixed timestep (`Fixed` / `FixedMain`) |
| Coyote time, jump buffer | Timer data on the entity or a small resource, consumed by the movement system |
| Collision response | Not in this stub. See bevy-physics-3d gaps |

## Gaps

- No verified character-controller type in the `bevy` 0.20.0 crate docs opened for this pass. The feature list has no physics solver.
- Do not call `move_and_slide`, `_physics_process`, or `CharacterBody2D`.
- Ground detection, shape casts, and collision layers are unverified. Do not invent query APIs.

## Related

- Hub: [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)
- Godot counterpart: [godot-characterbody-2d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-characterbody-2d/SKILL.md)
- Docs opened: https://bevy.org/learn/quick-start/getting-started/ecs/ and https://docs.rs/bevy/0.20.0/bevy/time/index.html
