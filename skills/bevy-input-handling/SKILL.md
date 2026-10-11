---
name: bevy-input-handling
description: "Docs-first stub for Bevy player input. Godot counterpart: godot-input-handling. Not a full port. Keywords: Bevy, ButtonInput, KeyCode, MouseButton, Gamepad."
---

# Bevy input handling (docs-first stub)

Not a full port. Input here is resources and events on the app, not an action map copied from Godot.

## When to use

Load this when a system should read keyboard, mouse, or gamepad state. The `bevy::input` module (docs.rs `latest`, crate 0.20.0) is the source for the names below.

## ECS shape

- **Plugin:** `InputPlugin` adds input from keyboard, mouse, gamepad, and touch. It ships inside the usual app plugins. `InputSystems` labels the systems that refresh that data.
- **Keyboard resource:** `Res<ButtonInput<KeyCode>>`. `KeyCode` is the physical key (layout-stable). `Res<ButtonInput<Key>>` is the logical key. The keyboard example uses `pressed`, `just_pressed`, and `just_released`.
- **Mouse:** `mouse_button_input_system` writes `ButtonInput<MouseButton>` from `MouseButtonInput`. `AccumulatedMouseMotion` and `AccumulatedMouseScroll` are resources reset every frame. `MouseMotion` and `MouseWheel` are the underlying events.
- **Gamepad:** `Gamepad` stores a connected pad's metadata (`GamepadButton`, `GamepadAxis`). Connection and axis changes arrive as `GamepadConnectionEvent`, `GamepadAxisChangedEvent`, and `GamepadButtonChangedEvent`. `GamepadRumbleRequest` is the force-feedback event.
- **Schedule:** read these resources from a system on `Update` (or a schedule you already chain). Do not invent an input-map resource.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Action just pressed | `ButtonInput::just_pressed` on `KeyCode` or `MouseButton` |
| Action held | `ButtonInput::pressed` |
| Physical WASD vs symbol keys | `KeyCode` for location, `Key` for the character |
| Mouse look delta | `AccumulatedMouseMotion` (reset each frame) |
| Controller | `Gamepad` plus the gamepad events listed above |

## Gaps

- Touch and gesture modules are listed on the input index. Their event fields were not opened.
- A project-wide action-map resource (named actions, rebinding) was not opened. Do not invent one.
- Glyphs and device prompts were not opened.

## NEVER

- No Godot input-map, event, or device types.
- No APIs this file did not open (`pressed`, `just_pressed`, `just_released` are the button methods cited).
- No third-party input crates.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/)  -  Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/)  -  Unversioned API index.
- [bevy::input](https://docs.rs/bevy/latest/bevy/input/index.html)  -  `ButtonInput`, `InputPlugin`, device modules.
- [ButtonInput](https://docs.rs/bevy/latest/bevy/input/struct.ButtonInput.html)  -  `pressed`, `just_pressed`, `just_released`, `KeyCode` and `Key`.
- [Mouse](https://docs.rs/bevy/latest/bevy/input/mouse/index.html)  -  `MouseButton`, motion and scroll resources.
- [Gamepad](https://docs.rs/bevy/latest/bevy/input/gamepad/index.html)  -  `Gamepad` and connection events.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples)  -  Example tree on the `latest` branch.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Who owns which piece of state.
- [bevy-ecs-composition](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-ecs-composition/SKILL.md)  -  Systems and `Query`.

#### Complements
- [bevy-character-movement](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-character-movement/SKILL.md)  -  Motion that consumes this input on the fixed timestep.
- [bevy-camera-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-camera-systems/SKILL.md)  -  Viewpoint that may read mouse motion.
- [godot-input-handling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-input-handling/SKILL.md)  -  Godot counterpart. Source idea only.

#### Downstream / consumers
- [bevy-audio-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-audio-systems/SKILL.md)  -  The audio control example reads `ButtonInput<KeyCode>` to pause and mute.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Bevy router.
