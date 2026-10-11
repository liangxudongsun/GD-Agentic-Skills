---
name: bevy-asset-scenes
description: "Docs-first stub for Bevy assets and scene spawning. Godot counterpart: godot-scene-management. Not a full port. Keywords: Bevy, AssetServer, Handle, Scene, bsn, spawn_scene."
---

# Bevy asset scenes (docs-first stub)

Not a full port. Levels are assets plus a `Scene` you spawn. They are not a packed Godot scene tree.

## When to use

Load this when content comes from disk or a scene description should spawn entities. `bevy::asset` and `bevy::scene` on docs.rs `latest` (0.20.0) are the sources.

## ECS shape

- **Assets:** `AssetServer` is the resource that loads from disk. `AssetServer::load` returns a `Handle` and does not reload while a strong handle still exists. Loaded data lives in `Assets<T>`. `AssetServer::is_loaded_with_dependencies` is true when the asset and its dependencies are ready. `LoadState` is the status type named on that page.
- **Handles:** strong handles are reference counted. Dropping the last strong handle removes the asset. Weak handles do not keep it alive. `Assets::add` inserts a procedural asset and does not deduplicate.
- **Hot reload:** the `file_watcher` Cargo feature, and `AssetPlugin`'s `watch_for_changes_override` field, are the toggles named on the asset index.
- **Scenes:** `bevy::scene` describes a `Scene` (entity, components, children, assets), built with the `bsn!` macro. `World::spawn_scene` and `Commands::spawn_scene` spawn immediately and error if asset dependencies are not loaded. `World::queue_spawn_scene` and `Commands::queue_spawn_scene` wait, then spawn in the `SpawnScene` schedule between `Update` and `PostUpdate`.
- **Hierarchy in a scene:** `Children [ ... ]` inside `bsn!`. Separate sibling entities with `--`. `#Name` assigns a `Name` inside that macro's scope.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Load a file | `AssetServer::load` → `Handle` |
| Wait until ready | `is_loaded_with_dependencies` before a state change |
| Instance a packed scene | `spawn_scene` or `queue_spawn_scene` around a `Scene` |
| Child nodes in that scene | `Children` inside `bsn!` |
| Change one entity's mesh | Swap the `Handle` on the component that stores it |

## Gaps

- `.bsn` asset files are described as future on the scene page. Do not invent a file loader for them.
- A `DynamicScene` type was not on docs.rs `latest` (the struct URL 404'd on 2026-10-11). Do not cite it.
- Scene change as "free the old level, then spawn the next" is a design note. No level-switch API was opened.
- Custom `AssetLoader` registration (`App::register_asset_loader`) was named, not opened as a worked example.

## NEVER

- No Godot packed-scene, node, or resource-loader types.
- No scene format this file did not open.
- No third-party scene crates.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/)  -  Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/)  -  Unversioned API index.
- [bevy::asset](https://docs.rs/bevy/latest/bevy/asset/index.html)  -  `AssetServer`, `Handle`, `Assets<T>`, load state, hot reload.
- [bevy::scene](https://docs.rs/bevy/latest/bevy/scene/index.html)  -  `Scene`, `bsn!`, `spawn_scene`, `queue_spawn_scene`, `SpawnScene`.
- [Assets](https://bevy.org/assets/)  -  Official asset catalog.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples)  -  Example tree on the `latest` branch.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Who owns which piece of state.
- [bevy-project-foundations](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-project-foundations/SKILL.md)  -  Cargo features, including asset watcher flags.
- [bevy-state-machines](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-state-machines/SKILL.md)  -  The asset page points at app states for load gates.

#### Complements
- [bevy-audio-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-audio-systems/SKILL.md)  -  Clips loaded through `AssetServer`.
- [bevy-save-load](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-save-load/SKILL.md)  -  Player saves are a separate gap from scene spawn.
- [godot-scene-management](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-scene-management/SKILL.md)  -  Godot counterpart. Source idea only.

#### Downstream / consumers
- [bevy-camera-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-camera-systems/SKILL.md)  -  Camera entities a scene may spawn.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Bevy router.
