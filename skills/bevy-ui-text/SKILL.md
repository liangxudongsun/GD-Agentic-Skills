---
name: bevy-ui-text
description: "Docs-first stub for Bevy UI text. Godot counterpart: godot-ui-rich-text. Keywords: Bevy, text, UI, Text, bevy_text, Text2d."
---

# Bevy UI text (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-ui-rich-text.

## When to use

Load this when a UI node or a 2D world label shows a string. Layout stays on bevy-ui-layout.

## ECS shape

- **UI:** the ui crate summary says spawn `Text` with `Node`.
- **Feature:** `bevy_text` provides text functionality. `default_font` includes a default ASCII font.
- **World text:** `Text2d` is on the sprite page, with `Text2dShadow`.
- **Systems:** `update_text2d_layout` is named on the sprite page for 2D text. UI text layout systems were not opened by name.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Label | Text on a UI node. |
| World label | Text2d. |
| Rich tags | Unverified. Do not invent BBCode. |

## Gaps

- The `bevy::text` module body was not opened. Font, span, and justification types are not named here.
- Rich-text effects and inline images were not opened.

## NEVER

- No Godot RichTextLabel or BBCode.

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
- [bevy::ui](https://docs.rs/bevy/latest/bevy/ui/index.html) - `Text` named in the crate summary.
- [bevy::sprite](https://docs.rs/bevy/latest/bevy/sprite/index.html) - `Text2d`.
- [bevy::text](https://docs.rs/bevy/latest/bevy/text/index.html) - Module exists via the `bevy_text` feature. Body not opened.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Hub and schedules.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md) - Components and systems.
- [bevy-ui-layout](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ui-layout/SKILL.md) - The node that holds the text.

#### Complements
- [bevy-dialogue-system](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-dialogue-system/SKILL.md) - Line strings.
- [godot-ui-rich-text](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-ui-rich-text/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
