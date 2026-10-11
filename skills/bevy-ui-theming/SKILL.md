---
name: bevy-ui-theming
description: "Docs-first stub for Bevy UI theming. Godot counterpart: godot-ui-theming. Keywords: Bevy, UI theme, BackgroundColor, BorderColor, feathers."
---

# Bevy UI theming (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-ui-theming.

## When to use

Load this when many nodes should share colors or a widget style. There is no Godot Theme resource in Bevy.

## ECS shape

- **Per-node colors opened:** `BackgroundColor`, `BorderColor`, `BorderRadius`, `BoxShadow`, `BackgroundGradient`.
- **Feature:** `bevy_feathers` is a collection of styled widgets for editors and inspectors. Widget names were not opened.
- **Window chrome:** `WindowTheme` is an enum on bevy::window for the window theme variant. That is OS window chrome, not a UI skin.
- **Systems:** you set components. No theme inheritance system was named.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Theme resource | Your own resource of colors, copied onto BackgroundColor. No Theme type was opened. |
| Style box | BorderRadius and BoxShadow on a Node. |
| Editor widgets | bevy_feathers exists. Do not assume it skins a game HUD. |

## Gaps

- No theme, stylebox, or font-theme type was opened under bevy::ui.
- Feathers widget pages were not opened.

## NEVER

- No Godot Theme or StyleBox types.

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
- [bevy::ui](https://docs.rs/bevy/latest/bevy/ui/index.html) - Color and radius components.
- [bevy::feathers](https://docs.rs/bevy/latest/bevy/feathers/index.html) - Editor widget collection. Body not opened.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-ui-layout](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ui-layout/SKILL.md) - Nodes being styled.

#### Complements
- [bevy-ui-text](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ui-text/SKILL.md) - Font choices stay a text gap.
- [godot-ui-theming](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-ui-theming/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
