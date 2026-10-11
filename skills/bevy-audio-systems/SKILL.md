---
name: bevy-audio-systems
description: "Docs-first stub for Bevy audio playback. Godot counterpart: godot-audio-systems. Not a full port. Keywords: Bevy, AudioPlayer, AudioSink, PlaybackSettings, AssetServer."
---

# Bevy audio systems (docs-first stub)

Not a full port. Sound is an entity with an `AudioPlayer` and a handle from `AssetServer`. Buses and Godot players are not mapped.

## When to use

Load this when a clip should start, loop, pause, or change volume. `bevy::audio` on docs.rs `latest` (0.20.0) and the `audio_control` example there are the sources.

## ECS shape

- **Play:** spawn `AudioPlayer::new(asset_server.load(...))`. `AudioPlayer<Source>` holds `Handle<Source>` where `Source: Asset + Decodable`. If the asset is not ready, playback starts when it is. `AudioPlayer` requires `PlaybackSettings`.
- **Settings:** `PlaybackSettings` configures the start. `PlaybackSettings::LOOP` and `.with_spatial(true)` appear in the spatial examples. Changes to `PlaybackSettings` do not affect audio that is already playing. `PlaybackMode` is `Once`, `Loop`, `Despawn`, or `Remove`.
- **Control:** when playback begins, Bevy inserts `AudioSink`. The control example queries `AudioSink` and calls `pause`, `toggle_mute`, `set_volume`, `set_speed`, and `position`. `SpatialAudioSink` is the spatial counterpart named on the playback page.
- **Replay:** after a non-looping sound finishes and the sink is drained, that `AudioPlayer` cannot be reused. Remove the audio components and add them again.
- **Schedule:** spawn on `Startup` or from a system that has `Res<AssetServer>` and `Commands`. Control systems in the example run where they read `ButtonInput<KeyCode>` and `Res<Time>`.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Play a file | `AudioPlayer::new` plus `AssetServer::load` |
| Loop | `PlaybackSettings::LOOP` |
| Pause / mute / volume while playing | `AudioSink` methods on the same entity |
| One-shot that should leave the world | `PlaybackMode::Despawn` or `Remove` |
| Positional emitter | `PlaybackSettings` with `with_spatial(true)` and `SpatialAudioSink` |

## Gaps

- Bus graphs, music/sfx mixer layouts, and audio-area shapes were not opened.
- Sample rates, supported file types, and the exact `AudioSource` type body were not opened beyond the `Handle` in `AudioPlayer::new`.
- Removing `AudioSink` restarts an attached source (stated on the sink page). A full restart recipe was not opened.

## NEVER

- No Godot audio player, bus, or stream types.
- No volume curves or mixer nodes this file did not open.
- No third-party audio crates.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/)  -  Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/)  -  Unversioned API index.
- [AudioPlayer](https://docs.rs/bevy/latest/bevy/audio/struct.AudioPlayer.html)  -  Component that starts a `Handle`.
- [PlaybackSettings](https://docs.rs/bevy/latest/bevy/audio/struct.PlaybackSettings.html)  -  Start settings; not live control.
- [PlaybackMode](https://docs.rs/bevy/latest/bevy/audio/enum.PlaybackMode.html)  -  `Once`, `Loop`, `Despawn`, `Remove`.
- [AudioSink](https://docs.rs/bevy/latest/bevy/audio/struct.AudioSink.html)  -  Live pause, mute, volume, speed.
- [Assets](https://bevy.org/assets/)  -  Official asset catalog.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples)  -  Example tree on the `latest` branch.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Who owns which piece of state.
- [bevy-asset-scenes](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-asset-scenes/SKILL.md)  -  `AssetServer` and `Handle`.

#### Complements
- [bevy-input-handling](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-input-handling/SKILL.md)  -  Keys the control example uses.
- [godot-audio-systems](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-audio-systems/SKILL.md)  -  Godot counterpart. Source idea only.

#### Downstream / consumers
- None yet. Genre skills that play stingers should route here when they exist.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Bevy router.
