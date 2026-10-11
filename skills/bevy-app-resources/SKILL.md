---
name: bevy-app-resources
description: "Docs-first stub for Bevy app-wide resources and schedules. Godot counterpart: godot-autoload-architecture. Not a full port. Keywords: Bevy, Resource, App, Schedule, Plugin."
---

# Bevy app resources (docs-first stub)

Not a full port. App-wide data is a `Resource` on the `World`. There is no autoload and no singleton node.

## When to use

Load this when data or logic must exist for the whole app: one clock, one ruleset, startup spawn, or an ordered pair of systems. Pair with bevy-data-resources for the component-versus-resource split.

## ECS shape

- **App.** The Apps page: an `App` contains a `World` and the outer loop. It initializes resources (one copy), adds systems to a `Schedule`, and imports other `App` changes through plugins.
- **Resources.** `Resource`, `Res`, `ResMut`, and `insert_resource` (Resources page). `Time` arrives from `add_plugins(DefaultPlugins)`.
- **Plugins.** The Resources page implements `Plugin` and inserts the resource inside `build`. `DefaultPlugins` is the plugin set that adds `Time`. Do not add further plugin names in this stub.
- **Schedules.** `add_systems(Startup, ...)` runs once before other systems. `add_systems(Update, ...)` is the repeating schedule in the ECS page. `.chain()` orders systems that must see each other's writes. `bevy::ecs::message` names `FixedUpdate` only as the schedule after which `signal_message_update_system` runs. Fixed-timestep clock types stay in bevy-character-movement.
- **States.** App-wide modes are `bevy::state`, not a global node. See bevy-state-machines.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Autoload singleton | A `Resource` inserted on the `App` |
| Global script that ticks | A system on `Update` (or a chained pair) |
| Boot setup | A `Startup` system or `insert_resource` in a `Plugin` |
| Cross-scene bus | A message or event. See bevy-events-messaging. Not a persistent node |

## Gaps

- Plugin dependency order and groups were not opened.
- Sub-apps were named on the state module (`SubApp`) and not opened here.
- Save-game resources and settings files were not opened (`bevy_settings` is a feature name on the crate page only).

## NEVER

- No autoload, singleton node, or signal bus.
- No Godot types.
- No invented plugin lists beyond `DefaultPlugins` and the `Plugin` trait the Resources page uses.
- No third-party crates.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/)  -  Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/)  -  Unversioned API index. `default_app` includes `bevy_state` and `bevy_log`.
- [Apps](https://bevy.org/learn/quick-start/getting-started/apps/)  -  `App`, `World`, resources, `Schedule`, plugins.
- [Resources](https://bevy.org/learn/quick-start/getting-started/resources/)  -  `Resource`, `insert_resource`, `Plugin::build`, `DefaultPlugins`, `Time`.
- [Quick Start: ECS](https://bevy.org/learn/quick-start/getting-started/ecs/)  -  `Startup`, `Update`, `add_systems`, `.chain()`.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples)  -  Example tree on the `latest` branch.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  No autoload layer on top of the schedule.
- [bevy-project-foundations](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-project-foundations/SKILL.md)  -  Crate and `App::new()`.

#### Complements
- [bevy-data-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-data-resources/SKILL.md)  -  When data is a component instead of a resource.
- [bevy-state-machines](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-state-machines/SKILL.md)  -  App-wide `States` instead of a global mode flag on a node.
- [godot-autoload-architecture](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-autoload-architecture/SKILL.md)  -  Godot counterpart. Source idea only. Do not import Godot types.

#### Downstream / consumers
- None yet. Save, audio, and scene skills are not ported.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Bevy router.
