---
name: bevy-save-load
description: "Docs-first stub for Bevy persistence boundaries. Godot counterpart: godot-save-load-systems. Not a full port. Keywords: Bevy, save, Resource, Scene, AssetServer, gaps."
---

# Bevy save and load (docs-first stub)

Not a full port. This file records what was opened and what was not. There is no Bevy save-slot API in the pages below.

## When to use

Load this when a design asks to persist player progress. Route asset and scene spawning to `bevy-asset-scenes`. Keep save bytes as an explicit gap until a current page names the format.

## ECS shape

- **What exists:** app-wide progress can be a `Resource` (see `bevy-data-resources`). Level content loads through `AssetServer` and may spawn with `spawn_scene` / `queue_spawn_scene` (`bevy::scene`, docs.rs `latest`, 0.20.0).
- **What was checked and rejected:** `https://docs.rs/bevy/latest/bevy/scene/struct.DynamicScene.html` returned 404 on 2026-10-11. The live scene index documents `Scene` and `bsn!`, not a save-file serializer. Do not call `DynamicScene::serialize` from this skill.
- **Schedule:** no save system is specified here. Do not invent a filesystem write inside `Update`.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Resource file for designer data | An asset `Handle`, or a `Resource` you own in code |
| Packed scene instance | `Scene` spawn on `bevy-asset-scenes` |
| Player save slot | Not opened. Leave it as data you have not serialized yet |

## Gaps

- No save path, slot index, version field, or RON/JSON writer was opened on docs.rs `latest`.
- Scene spawn is not a save game. Do not treat `bsn!` as a user save.
- Wasm has no general filesystem story on the pages opened for this batch. Do not invent one.

## NEVER

- No Godot `Resource`, `FileAccess`, or config-file types.
- No `DynamicScene` or scene-file writer this file's opened pages do not list.
- No third-party save crates.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped` because the gap was checked against live docs.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/)  -  Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/)  -  Unversioned API index.
- [bevy::scene](https://docs.rs/bevy/latest/bevy/scene/index.html)  -  Spawn API that is not a save format. `DynamicScene` struct URL 404.
- [bevy::asset](https://docs.rs/bevy/latest/bevy/asset/index.html)  -  Disk assets, not player slots.
- [Resources](https://bevy.org/learn/quick-start/getting-started/resources/)  -  App-wide data that a future save would have to name.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples)  -  Example tree on the `latest` branch.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Who owns which piece of state.
- [bevy-data-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-data-resources/SKILL.md)  -  `Resource` versus `Component`.
- [bevy-asset-scenes](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-asset-scenes/SKILL.md)  -  Loading content. Not a save slot.

#### Complements
- [godot-save-load-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-save-load-systems/SKILL.md)  -  Godot counterpart. Source idea only.

#### Downstream / consumers
- None until a save format is opened.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Bevy router.
