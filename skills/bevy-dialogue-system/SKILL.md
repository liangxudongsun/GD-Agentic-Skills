---
name: bevy-dialogue-system
description: "Docs-first stub for Bevy dialogue. Godot counterpart: godot-dialogue-system. Keywords: Bevy, dialogue, lines, ECS, UI text."
---

# Bevy dialogue system (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-dialogue-system.

## When to use

Load this when lines, choices, or speaker ids advance. Rendering the line is bevy-ui-text.

## ECS shape

- **Components:** a line id and a speaker id that you define.
- **Resources:** run-wide tables live in a resource (bevy-data-resources), not an autoload.
- **Systems:** mutate those components on `Update` or the fixed timestep. Use `.chain()` when damage must land before death.
- **Messages:** one-shot facts (hit, pickup, quest advance) go through bevy-events-messaging. This file does not add a new event type name.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Line table | A resource of ids and strings. |
| Current line | A component or resource cursor. |
| Portrait | An image handle via bevy-asset-scenes. Layout is bevy-ui-layout. |

## Gaps

- No dialogue, bark, or choice type exists in the opened Bevy modules.
- Rich text tags inside a line are a gap on bevy-ui-text.

## NEVER

- No Godot node, resource, or signal types for this mechanic.

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
- [bevy-ui-text](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ui-text/SKILL.md) - Draw the line.
- [bevy-quest-system](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-quest-system/SKILL.md) - Quest gates.
- [bevy-data-resources](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-data-resources/SKILL.md) - Tables and definitions.
- [bevy-events-messaging](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-events-messaging/SKILL.md) - One-shot facts.

#### Complements
- [bevy-state-machines](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-state-machines/SKILL.md) - Mode flags.
- [godot-dialogue-system](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-dialogue-system/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
