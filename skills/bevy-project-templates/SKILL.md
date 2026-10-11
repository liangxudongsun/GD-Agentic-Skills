---
name: bevy-project-templates
description: "Docs-first stub for Bevy project templates. Godot counterpart: godot-project-templates. Keywords: Bevy, template, cargo, features, 2d, 3d, ui."
---

# Bevy project templates (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-project-templates.

## When to use

Load this when choosing a starting Cargo feature set. App construction details stay on bevy-project-foundations. This file does not ship a template repository.

## ECS shape

- **Profiles opened on the crate page:** `default` (2d, 3d, ui, audio), `2d`, `3d`, `ui`. Example snippet shows `default-features = false` plus a profile feature. The sample version string on that page said 0.18; the pin on bevy-master stays 0.20.0.
- **Minimal app:** the crate docs show `App::new().add_systems(Update, ...).run()`.
- **Windowed games:** `DefaultPlugins` remains the plugin set named on the plugins page.
- **No repo:** do not invent a template URL.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| 2D starter | Cargo feature profile 2d plus DefaultPlugins. |
| 3D starter | Profile 3d. |
| UI tool | Profile ui. Feathers is optional and unopened. |
| Headless | default_app is described as a baseline without a renderer. Server networking stays blocked. |

## Gaps

- Official example binaries were not copied. Link the examples tree only.
- Gitignore and CI files were not opened.

## NEVER

- No Godot project.godot template or export presets.

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
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub.
- [bevy-project-foundations](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-project-foundations/SKILL.md) - Cargo app shell.

#### Complements
- [bevy-platform-desktop](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-platform-desktop/SKILL.md) - Windowed targets.
- [godot-project-templates](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-project-templates/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
