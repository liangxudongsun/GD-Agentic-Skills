---
name: bevy-physics-3d
description: "Docs-first stub for Bevy 3D physics. Godot counterpart: godot-physics-3d. Not a full port. Keywords: Bevy, physics, ECS, 3D."
---

# Bevy 3D physics (docs-first stub)

Not a full port. No Rust crate in this phase.

## When to use

Load this when a Bevy app needs simulated 3D bodies (props, impulses, constraints) and you need the gap list before choosing a solver. Pair with bevy-character-movement for player motion that should not be a rigid body.

## ECS shape

- **Components** would own body kind, velocity, and collider data once a solver crate is chosen. The ECS page only shows plain `Component` structs. It does not define a rigid body.
- **Resources** would own gravity and solver settings. Not specified in the pages opened here.
- **Systems** would step the solver on a fixed schedule. `bevy::time` 0.20.0 documents `Fixed` and `run_fixed_main_schedule` (`FixedMain`). That is a clock, not a physics engine.
- **Schedule:** fixed timestep for the step; `.chain()` when a system must see the step result before it runs (ECS page).

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Simulated prop | Entity plus solver-defined components, after a crate is verified |
| Player locomotion | Not a rigid body. Use bevy-character-movement |
| Joints, ragdolls, bones driven by physics | Unverified. Leave out until a solver page is opened |
| Layers and masks | Unverified. Do not copy Godot bit names |

## Gaps

- The `bevy` 0.20.0 crate feature list opened on docs.rs has no physics-engine feature. Jolt, a Godot physical-bone type, and Godot joint types are not Bevy names. Do not pretend those APIs exist.
- Third-party plugins are allowed by the plugins page (add a crate, then `add_plugins`). This pass did not open a specific 3D physics crate, so no plugin path is recorded.
- Raycasts, CCD, and collision events are unverified.

## Related

- Hub: [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)
- Movement stub: [bevy-character-movement](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-character-movement/SKILL.md)
- Godot counterpart: [godot-physics-3d](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-physics-3d/SKILL.md)
- Docs opened: https://docs.rs/bevy/0.20.0/bevy/ and https://bevy.org/learn/quick-start/getting-started/plugins/ and https://docs.rs/bevy/0.20.0/bevy/time/index.html
