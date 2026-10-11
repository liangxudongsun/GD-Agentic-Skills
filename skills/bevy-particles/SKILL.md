---
name: bevy-particles
description: "Docs-first stub for Bevy particle effects. Godot counterpart: godot-particles. Keywords: Bevy, particles, VFX, gaps, ECS."
---

# Bevy particles (docs-first stub)

Not a full port. Docs-first stub. Godot counterpart: godot-particles.

## When to use

Load this before adding a burst, trail, or GPU particle effect so the gap is explicit. Do not invent a particle plugin.

## ECS shape

- **Components** would own emitter settings once a particle type exists. None was on the crate index.
- **Resources:** none named for particles.
- **Systems:** none named.
- **Schedule:** a future emitter would run on `Update` or a fixed step. That is a placement note, not an API.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| CPU particles | Unverified. No particle module in the 0.20.0 module list. |
| GPU particles | Unverified. Same gap. |
| One-shot burst | Your own timer component until a particle page is opened. |

## Gaps

- The opened `bevy` 0.20.0 module and feature lists have no particle feature and no particle module.
- No third-party particle crate was selected from the assets page.

## NEVER

- No Godot particle node types.
- No named particle crate as the chosen solution.

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

#### Complements
- [bevy-shaders](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-shaders/SKILL.md) - Materials are not a particle system.
- [godot-particles](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-particles/SKILL.md) - Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md) - Bevy router.
