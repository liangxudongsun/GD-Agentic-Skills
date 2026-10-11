---
name: bevy-state-machines
description: "Docs-first stub for Bevy app states and per-entity state data. Godot counterpart: godot-state-machine-advanced. Not a full port. Keywords: Bevy, States, NextState, OnEnter."
---

# Bevy state machines (docs-first stub)

Not a full port. The opened API is app-wide states in `bevy::state` 0.20.0. A per-entity graph is data plus systems, not a second engine type.

## When to use

Load this when the app needs a large-scale mode (paused, in a menu, loading) or when one entity needs a small mode flag. Use `bevy::state` for the first. Use a component for the second. Do not merge them into one Godot-style state graph.

## ECS shape

- **App states.** `bevy::state`: states are app-wide finite state machines. Three types implement `States`.
  - Standard states change only by setting the `NextState<S>` resource.
  - `SubStates` also use `NextState<S>`, and are removed from the `World` when source states are not in the required state.
  - `ComputedStates` derive from other states through a `compute` method.
- **Transition schedules.** `OnEnter<S>`, `OnExit<S>`, and `OnTransition<S>` run systems on matching transitions. `StateTransitionEvent<S>` fires when state `S` changes. Run conditions: `in_state<S>` and `state_changed<S>`.
- **Entity lifetime.** `DespawnOnEnter<S>` and `DespawnOnExit<S>` despawn entities on those transitions (`state_scoped`).
- **Feature.** The `bevy` 0.20.0 crate page includes `bevy_state` in the `default_app` collection. The state module was opened; `App` installation method names were not. Do not invent `init_state` or similar.
- **Per-entity mode.** Store an enum in a `Component` and branch in a system (`Query` from the ECS page). No per-entity state-machine type was opened.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| App mode (menu, pause, play) | A `States` type and `NextState<S>` |
| Run logic only in one mode | `in_state` or an `OnEnter` / `OnExit` / `OnTransition` schedule |
| Child mode that exists only inside a parent mode | `SubStates` |
| Mode derived from other modes | `ComputedStates` |
| One actor's animation or combat mode | An enum `Component` plus a system. Not `States` unless it is truly app-wide |

## Gaps

- State installation methods on `App` were not opened (`bevy::state::app` is listed, not read).
- The states, sub-states, and computed-state examples named by the module were not opened.
- Hierarchical per-entity graphs, transition tables, and animation state machines were not opened.

## NEVER

- No Godot animation-tree or node state-machine types.
- No invented `App` state-setup methods.
- No third-party crates.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/)  -  Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/)  -  `bevy_state` ships inside the `default_app` collection.
- [bevy::state](https://docs.rs/bevy/latest/bevy/state/index.html)  -  `States`, `NextState`, `SubStates`, `ComputedStates`, transition schedules, `StateTransitionEvent`, `in_state`, `state_changed`, `DespawnOnEnter`, `DespawnOnExit`.
- [Quick Start: ECS](https://bevy.org/learn/quick-start/getting-started/ecs/)  -  `Component` and `Query` for a per-entity mode flag.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples)  -  Example tree on the `latest` branch. State examples were not opened.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Schedules versus a scene tree.
- [bevy-data-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-data-resources/SKILL.md)  -  `NextState<S>` is a resource. Per-entity modes are components.

#### Complements
- [bevy-events-messaging](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-events-messaging/SKILL.md)  -  Messages and observers that are not state transitions.
- [godot-state-machine-advanced](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-state-machine-advanced/SKILL.md)  -  Godot counterpart. Source idea only. Do not import Godot types.

#### Downstream / consumers
- [bevy-character-movement](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-character-movement/SKILL.md)  -  Actor motion. A jump or ground mode stays a component unless you opened a reason to use `States`.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Bevy router.
