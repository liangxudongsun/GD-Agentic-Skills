---
name: bevy-ui-layout
description: "Docs-first stub for Bevy UI layout. Godot counterpart: godot-ui-containers. Keywords: Bevy, UI, Node, Flexbox, BackgroundColor, Button."
---

# Bevy UI layout (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-ui-containers.

## When to use

Load this when laying out HUD or menu nodes. Text content stays on bevy-ui-text. Colors and widget styling stay on bevy-ui-theming.

## ECS shape

- **Crate text (opened):** spawn UI with `widget::Button`, `ImageNode`, `Text`, and `Node`. Layout uses Flexbox and CSS Grid.
- **Components named:** `Node`, `BackgroundColor`, `BorderColor`, `BorderRadius`, `ComputedNode`, `GridPlacement`, `GridTrack`, `GlobalZIndex`.
- **Feature:** `bevy_ui` is a custom ECS-driven UI framework.
- **Systems:** layout and update systems are engine-owned (`bevy::ui::update` exists). Do not write a second layout pass.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Container | A Node entity. Children are child entities, not Control nodes. |
| Button | widget::Button as named in the crate summary. |
| Image | ImageNode as named in the crate summary. |
| Grid | GridTrack and GridPlacement. |

## Gaps

- Flex property field names on `Node` were not opened. Do not invent `justify_content` spellings.
- `bevy_feathers` is a styled widget collection for editors. Its widget list was not opened. Do not treat it as game HUD theme.

## NEVER

- No Godot Control, Container, or anchor types.

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
- [bevy::ui](https://docs.rs/bevy/latest/bevy/ui/index.html) - `Node`, Flexbox and CSS Grid, `widget::Button`, `ImageNode`, `Text`.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.

#### Complements
- [bevy-ui-text](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ui-text/SKILL.md) - Text on a node.
- [bevy-ui-theming](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ui-theming/SKILL.md) - Colors and backgrounds.
- [godot-ui-containers](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-ui-containers/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- [bevy-ui-text](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ui-text/SKILL.md) - Consumes layout nodes.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
