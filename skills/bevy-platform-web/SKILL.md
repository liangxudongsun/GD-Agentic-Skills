---
name: bevy-platform-web
description: "Docs-first stub for Bevy web and Wasm. Godot counterpart: godot-platform-web. Keywords: Bevy, wasm, web, webgl2, webgpu, browser."
---

# Bevy web platform (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-platform-web.

## When to use

Load this when the same app should run in a browser. Packaging pipelines are not specified here.

## ECS shape

- **Features opened:** `web` (browser APIs, wasm32 only), `webgl2` (limitations so Wasm can use WebGL2), `webgpu` (overrides webgl2; Wasm with WebGPU only).
- **Asset note:** `http` and `https` features enable remote asset download and warn about security. `web_asset_cache` caches downloads and currently never invalidates entries.
- **Clipboard:** `clipboard_image` says it is not supported on WASM.
- **Window:** the same `Window` component still describes the canvas window. DOM integration was not opened.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| HTML5 export | A wasm32 build with the web feature. Toolchain steps were not opened. |
| WebGL vs WebGPU | webgl2 versus webgpu features. They conflict as documented. |
| Remote assets | http or https features. Security warning is on the feature list. |

## Gaps

- wasm-bindgen, trunk, or other bundler steps were not opened. Do not invent commands.
- Canvas sizing hooks were not opened.

## NEVER

- No Godot HTML5 export preset names.

- No Godot types in Bevy code.
- No invented APIs or unnamed third-party crates as the chosen solver.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/) - Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/) - Unversioned API index. Feature list opened for 0.20.0.
- [Assets](https://bevy.org/assets/) - Official asset catalog. No third-party crate was selected.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples) - Example tree on the `latest` branch.
- [ECS](https://bevy.org/learn/quick-start/getting-started/ecs/) - `Component`, systems, `Query`, `Startup`, `Update`, and `.chain()`.
- [Plugins](https://bevy.org/learn/quick-start/getting-started/plugins/) - `Plugin`, `DefaultPlugins`, `MinimalPlugins`, and `add_plugins`.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-platform-desktop](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-platform-desktop/SKILL.md) - Window component shared with desktop.

#### Complements
- [godot-platform-web](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-platform-web/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
