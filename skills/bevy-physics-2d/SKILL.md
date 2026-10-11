---
name: bevy-physics-2d
description: "Docs-first stub for Bevy 2D physics. Godot counterpart: godot-2d-physics. Not a full port. Keywords: Bevy, physics, 2D, ECS, collision, gaps."
---

# Bevy 2D physics (docs-first stub)

Not a full port. No Rust crate in this phase. No solver was chosen.

## When to use

Load this when a Bevy app needs simulated 2D bodies, triggers, or layer filtering and you need the gap list before choosing a solver. Pair with bevy-character-movement for player motion that should not be a rigid body. Pair with bevy-spatial-queries for casts that also wait on a solver.

## ECS shape

- **Components** would own body kind, velocity, and collider data once a solver crate is chosen. The ECS page only shows plain `Component` structs. It does not define a rigid body.
- **Resources** would own gravity and solver settings. Not specified in the pages opened here.
- **Systems** would step the solver on a fixed schedule. `bevy::time` documents `Fixed` and `run_fixed_main_schedule` (`FixedMain`). That is a clock, not a physics engine.
- **Schedule:** fixed timestep for the step; `.chain()` when a system must see the step result before it runs (ECS page).

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Simulated 2D prop | Entity plus solver-defined components, after a crate is verified |
| Player locomotion | Not a rigid body. Use bevy-character-movement |
| Trigger volumes | Unverified. Leave out until a solver page is opened |
| Layers and masks | Unverified. Do not copy Godot bit names |

## Gaps

- The `bevy` 0.20.0 crate feature list opened on docs.rs has no physics-engine feature. 2D collision shapes, layers, and masks are not Bevy names in the pages opened here.
- Third-party plugins are allowed by the plugins page (add a crate, then `add_plugins`). This pass did not open a specific 2D physics crate, so no plugin path is recorded.
- Raycasts, CCD, and collision events are unverified. Route query design to bevy-spatial-queries, which has the same solver gap.

## NEVER

- No Godot 2D physics node or server types.
- No Avian, Rapier, or any other named physics crate as the chosen solver.
- No invented collider, layer, or joint APIs.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/) - Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/) - Unversioned API index. The opened 0.20.0 feature list had no physics-engine feature.
- [Assets](https://bevy.org/assets/) - Official asset catalog. No physics plugin was selected from it on this pass.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples) - Example tree on the `latest` branch.
- [Quick Start: plugins](https://bevy.org/learn/quick-start/getting-started/plugins/) - `Plugin`, `DefaultPlugins`, `MinimalPlugins`, and third-party `add_plugins`.
- [ECS](https://bevy.org/learn/quick-start/getting-started/ecs/) - `Component`, systems, `Query`, `Startup`, `Update`, and `.chain()`.
- [bevy::time](https://docs.rs/bevy/latest/bevy/time/index.html) - `Fixed` and `run_fixed_main_schedule` (`FixedMain`) as a clock, not a solver.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - ECS ownership and the fixed-timestep schedule names this stub is allowed to use.

#### Complements
- [bevy-physics-3d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-physics-3d/SKILL.md) - Same solver gap in 3D.
- [bevy-character-movement](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-character-movement/SKILL.md) - Player locomotion that should not be a rigid body.
- [bevy-spatial-queries](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-spatial-queries/SKILL.md) - Casts and overlaps. Also blocked on a solver.
- [godot-2d-physics](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-2d-physics/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet. Combat and shooter skills are not ported.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
