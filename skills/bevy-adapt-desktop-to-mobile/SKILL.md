---
name: bevy-adapt-desktop-to-mobile
description: "Docs-first stub for adapting a Bevy desktop game to mobile. Godot counterpart: godot-adapt-desktop-to-mobile. Keywords: Bevy, mobile, touch, UI, adapt."
---

# Bevy adapt desktop to mobile (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-adapt-desktop-to-mobile.

## When to use

Load this when a desktop window game must accept touch and a smaller layout. Platform features are on bevy-platform-mobile.

## ECS shape

- **Input:** `touch` and `gestures` features exist. Action mapping is still a gap on bevy-input-handling.
- **UI:** scale nodes with `Node` layout. A dpi component was not opened. `WindowResolution` and scale-factor events exist on the window page (`WindowScaleFactorChanged`).
- **Textures:** ASTC is mentioned only as a compression feature blurb.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Mouse | Touch feature. Pointer unification was not opened. |
| Hover menus | Replace hover-only actions. UI picking exists as `ui_picking` but behavior was not opened. |
| Safe margins | Unverified. |

## Gaps

- No control-scheme or safe-area resource was opened.
- Store and permission steps were not opened.

## NEVER

- No Godot export-preset or touch emulation names.

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
- [bevy-platform-mobile](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-platform-mobile/SKILL.md) - Android and touch features.
- [bevy-ui-layout](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ui-layout/SKILL.md) - Reflow the HUD.

#### Complements
- [bevy-adapt-mobile-to-desktop](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-adapt-mobile-to-desktop/SKILL.md) - The reverse adapt.
- [godot-adapt-desktop-to-mobile](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-adapt-desktop-to-mobile/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
