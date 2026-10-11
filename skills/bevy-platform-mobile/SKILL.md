---
name: bevy-platform-mobile
description: "Docs-first stub for Bevy mobile. Godot counterpart: godot-platform-mobile. Keywords: Bevy, mobile, android, touch, ASTC, gestures."
---

# Bevy mobile platform (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-platform-mobile.

## When to use

Load this when targeting touch devices. Safe-area and store-listing steps were not opened. XR is not this skill.

## ECS shape

- **Input features:** `touch` (enabled by bevy_window) and `gestures` (enabled by bevy_window).
- **Android:** `android-game-activity` is the default Android activity. `android-native-activity` is marked legacy.
- **Textures:** `compressed_image_saver` mentions ASTC for mobile via an environment variable. The variable name's behavior was not opened beyond that blurb.
- **Log:** `bevy::log` says it configures platform log handlers including Android. Handler setup was not opened.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Touch | The touch feature. Button mapping was not opened. See bevy-input-handling for keyboard and mouse. |
| Android activity | android-game-activity feature. |
| Safe area | Unverified. No safe-area type was on the window page summary. |

## Gaps

- iOS-specific features were not named in the opened feature list except `ScreenEdge` on the window page, which documents a winit iOS screen-edge correspondence. Rules were not opened.
- Store packaging, permissions, and safe-area insets were not opened.

## NEVER

- No Godot touch-screen or safe-margin project settings.

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
- [bevy::window](https://docs.rs/bevy/latest/bevy/window/index.html) - `ScreenEdge` mentions winit iOS. Touch events were not listed as their own struct in the opened summary.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-input-handling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-input-handling/SKILL.md) - Other devices.
- [bevy-platform-desktop](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-platform-desktop/SKILL.md) - Window shell.

#### Complements
- [bevy-adapt-desktop-to-mobile](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-adapt-desktop-to-mobile/SKILL.md) - Layout and input adapt.
- [godot-platform-mobile](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-platform-mobile/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
