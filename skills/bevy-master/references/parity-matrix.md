# Parity matrix (living)

Full inventory coverage: all 99 Godot skills from the Forge inventory have one row. Phase-1 seed rows stay (paths, docs_mapped, blockers). No new-engine-only skills.

Schema lock stays in Forge. This file is the product copy agents load with `bevy-master`. Godot is source of truth. No Bevy skill without a Godot counterpart or an explicit new-engine need.

`blocked` / `revisit` / `n_a_godot_only` / `parked` require `blocker` and `revisit_after`.

`script_port`: `n/a` | `gdscript_to_rust` | `python_to_rust` | `keep_python_tooling` | `blocked`.

`docs_mapped` means docs were checked and linked. It is not a port.

Columns: skill_id, godot_path, godot_status, bevy_path, bevy_status, blocker, revisit_after, script_port, docs_refs, notes.

| skill_id | godot_path | godot_status | bevy_path | bevy_status | blocker | revisit_after | script_port | docs_refs | notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| godot-master | `skills/godot-master/SKILL.md` | present | `skills/bevy-master/SKILL.md` | docs_mapped |  |  | n/a | https://docs.rs/bevy/latest/bevy/ https://bevy.org/learn/quick-start/getting-started/ecs/ | Greenlit 2026-10-11. Phase-1 hub scaffold. Not a second master over Godot. Bevy 0.20.0. docs.rs links use `latest`. |
| godot-analyst | `skills/godot-analyst/SKILL.md` | present |  | n_a_godot_only | Godot project audit (ResourceLoader, scene graph) | after-bevy-audit-need | n/a |  | No twin until proven. |
| godot-auditor | `skills/godot-auditor/SKILL.md` | present |  | n_a_godot_only | Godot never-list / ObjectDB | after-bevy-audit-need | n/a |  | No twin until proven. |
| godot-builder | `skills/godot-builder/SKILL.md` | present |  | n_a_godot_only | Godot CLI / headless editor | after-bevy-cli-proven | n/a |  | No twin until a Bevy CLI need is proven. |
| godot-autoload-architecture | `skills/godot-autoload-architecture/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | App-wide resources and schedules later. No AutoLoad stub this phase. |
| godot-composition | `skills/godot-composition/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Godot composition is not Bevy ECS. A later row must teach bundles and systems. |
| godot-composition-apps | `skills/godot-composition-apps/SKILL.md` | present |  | n_a_godot_only | Godot EditorPlugin / Control-app composition | after-bevy-app-ui-need | n/a |  | No twin. Gameplay composition stays on the ECS row. |
| godot-debugging-profiling | `skills/godot-debugging-profiling/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Profiler and diagnostics later. No stub this phase. |
| godot-gdscript-mastery | `skills/godot-gdscript-mastery/SKILL.md` | present |  | n_a_godot_only | language skill; Bevy gameplay runtime is Rust | after-bevy-0.x-rust-skill | n/a |  | No Bevy body. |
| godot-project-foundations | `skills/godot-project-foundations/SKILL.md` | present |  | not_started |  |  | n/a |  | Feature folders and naming. No stub this phase. |
| godot-project-templates | `skills/godot-project-templates/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre scaffolds later. No stub this phase. |
| godot-resource-data-patterns | `skills/godot-resource-data-patterns/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Data as components and resources. No `.tres` twin. |
| godot-signal-architecture | `skills/godot-signal-architecture/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Map to Bevy messages, events, or observers only after the docs pin. No stub yet. |
| godot-state-machine-advanced | `skills/godot-state-machine-advanced/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | States as components or enums plus systems. No stub yet. |
| godot-version-migration | `skills/godot-version-migration/SKILL.md` | present |  | n_a_godot_only | Godot hop history | after-bevy-version-hub | n/a |  | No Bevy body. A Bevy version hub is a later explicit new-engine need, not this row. |
| godot-2d-animation | `skills/godot-2d-animation/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Sprite and cutout animation later. No stub this phase. |
| godot-2d-physics | `skills/godot-2d-physics/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Startable later. Not a Phase-1 stub. |
| godot-animation-player | `skills/godot-animation-player/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Timeline animation later. No stub this phase. |
| godot-animation-tree-mastery | `skills/godot-animation-tree-mastery/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Animation graph later. No stub this phase. |
| godot-camera-systems | `skills/godot-camera-systems/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Camera follow and shake later. No stub this phase. |
| godot-characterbody-2d | `skills/godot-characterbody-2d/SKILL.md` | present | `skills/bevy-character-movement/SKILL.md` | docs_mapped |  |  | gdscript_to_rust | https://bevy.org/learn/quick-start/getting-started/ecs/ https://docs.rs/bevy/latest/bevy/time/index.html | Phase-1 starter. Docs-first. Coyote time and jump buffer are design notes, not a Node port. |
| godot-particles | `skills/godot-particles/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Particle effects later. No stub this phase. |
| godot-shaders-basics | `skills/godot-shaders-basics/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Materials and shaders later. No stub this phase. |
| godot-tilemap-mastery | `skills/godot-tilemap-mastery/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Tile maps later. No stub this phase. |
| godot-tweening | `skills/godot-tweening/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Tween and juice later. No stub this phase. |
| godot-3d-lighting | `skills/godot-3d-lighting/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Lights and environment later. No stub this phase. |
| godot-3d-materials | `skills/godot-3d-materials/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | PBR materials later. No stub this phase. |
| godot-3d-world-building | `skills/godot-3d-world-building/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Level assembly later. No stub this phase. |
| godot-navigation-pathfinding | `skills/godot-navigation-pathfinding/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Navigation later. No stub this phase. |
| godot-physics-3d | `skills/godot-physics-3d/SKILL.md` | present | `skills/bevy-physics-3d/SKILL.md` | docs_mapped |  |  | gdscript_to_rust | https://docs.rs/bevy/latest/bevy/ https://bevy.org/learn/quick-start/getting-started/plugins/ | Phase-1 starter. Docs-first. Do not pretend Jolt, PhysicalBone, or Joint3D APIs exist in Bevy. |
| godot-procedural-generation | `skills/godot-procedural-generation/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Seeded generation later. No stub this phase. |
| godot-raycasting-queries | `skills/godot-raycasting-queries/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Spatial queries later. Solver crate stays unpicked. |
| godot-ability-system | `skills/godot-ability-system/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Ability components later. No stub this phase. |
| godot-combat-system | `skills/godot-combat-system/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Hit and damage components later. No stub this phase. |
| godot-dialogue-system | `skills/godot-dialogue-system/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Dialogue data later. No stub this phase. |
| godot-economy-system | `skills/godot-economy-system/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Currency and loot data later. No stub this phase. |
| godot-game-loop-collection | `skills/godot-game-loop-collection/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Collectible loop later. No stub this phase. |
| godot-game-loop-harvest | `skills/godot-game-loop-harvest/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Harvest loop later. No stub this phase. |
| godot-game-loop-time-trial | `skills/godot-game-loop-time-trial/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Time-trial loop later. No stub this phase. |
| godot-game-loop-waves | `skills/godot-game-loop-waves/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Wave loop later. No stub this phase. |
| godot-inventory-system | `skills/godot-inventory-system/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Inventory components later. No stub this phase. |
| godot-mechanic-revival | `skills/godot-mechanic-revival/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Revival loop later. No stub this phase. |
| godot-mechanic-secrets | `skills/godot-mechanic-secrets/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Secret flags later. No stub this phase. |
| godot-monte-carlo-balancer | `skills/godot-monte-carlo-balancer/SKILL.md` | present |  | revisit | tooling twin not stubbed this wave; balance lab stays Godot-side | after-bevy-tooling-need | keep_python_tooling |  | Existing Rust lab is Godot-side. Not a Bevy port. |
| godot-quest-system | `skills/godot-quest-system/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Quest data later. No stub this phase. |
| godot-rpg-stats | `skills/godot-rpg-stats/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Stat components later. No stub this phase. |
| godot-save-load-systems | `skills/godot-save-load-systems/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Save resources later. No stub this phase. |
| godot-scene-management | `skills/godot-scene-management/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Asset scenes later. No stub this phase. |
| godot-turn-system | `skills/godot-turn-system/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Turn schedule later. No stub this phase. |
| godot-agent-vision | `skills/godot-agent-vision/SKILL.md` | present |  | revisit | tooling twin not stubbed this wave; host capture stays Python | after-bevy-tooling-need | keep_python_tooling |  | Host capture may stay Python. Do not stub a twin. |
| godot-input-handling | `skills/godot-input-handling/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Input actions later. No stub this phase. |
| godot-ui-containers | `skills/godot-ui-containers/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | UI layout later. No stub this phase. |
| godot-ui-rich-text | `skills/godot-ui-rich-text/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | UI text later. No stub this phase. |
| godot-theme-easter | `skills/godot-theme-easter/SKILL.md` | present |  | n_a_godot_only | Godot Theme seasonal overlay | after-bevy-ui-theme-need | n/a |  | No twin. Seasonal Theme injection is Godot chrome. |
| godot-ui-theming | `skills/godot-ui-theming/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | UI theme later. No stub this phase. |
| godot-audio-systems | `skills/godot-audio-systems/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Audio later. No stub this phase. |
| godot-export-builds | `skills/godot-export-builds/SKILL.md` | present |  | n_a_godot_only | export-template certification; no Bevy packaging twin yet | after-bevy-packaging-proven | n/a |  | No twin until a Bevy packaging need is proven. |
| godot-multiplayer-networking | `skills/godot-multiplayer-networking/SKILL.md` | present |  | blocked | networking ownership not opened; no Bevy netcode choice yet | 2026-11-11 | blocked |  | No Bevy body. |
| godot-performance-optimization | `skills/godot-performance-optimization/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Budgets and culling later. No stub this phase. |
| godot-platform-console | `skills/godot-platform-console/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Console certification later. No stub this phase. |
| godot-platform-desktop | `skills/godot-platform-desktop/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Desktop windowing later. No stub this phase. |
| godot-platform-mobile | `skills/godot-platform-mobile/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Touch and safe area later. No stub this phase. |
| godot-platform-vr | `skills/godot-platform-vr/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | XR later. No stub this phase. |
| godot-platform-web | `skills/godot-platform-web/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Web export later. No stub this phase. |
| godot-server-architecture | `skills/godot-server-architecture/SKILL.md` | present |  | blocked | same networking hold as multiplayer | 2026-11-11 | blocked |  | No Bevy body. |
| godot-testing-patterns | `skills/godot-testing-patterns/SKILL.md` | present |  | n_a_godot_only | GdUnit4-only testing until a Bevy test story is proven | after-bevy-test-story | n/a |  | No twin until cargo-test / Bevy test docs are opened. |
| godot-adapt-2d-to-3d | `skills/godot-adapt-2d-to-3d/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Dimension adapt later. No stub this phase. |
| godot-adapt-3d-to-2d | `skills/godot-adapt-3d-to-2d/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Dimension adapt later. No stub this phase. |
| godot-adapt-desktop-to-mobile | `skills/godot-adapt-desktop-to-mobile/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Input and scale adapt later. No stub this phase. |
| godot-adapt-mobile-to-desktop | `skills/godot-adapt-mobile-to-desktop/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Input and scale adapt later. No stub this phase. |
| godot-adapt-single-to-multiplayer | `skills/godot-adapt-single-to-multiplayer/SKILL.md` | present |  | blocked | networking ownership not opened; no Bevy netcode choice yet | 2026-11-11 | blocked |  | No Bevy body. |
| godot-genre-action-rpg | `skills/godot-genre-action-rpg/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-fighting | `skills/godot-genre-fighting/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-platformer | `skills/godot-genre-platformer/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-shooter | `skills/godot-genre-shooter/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-shooter-fps | `skills/godot-genre-shooter-fps/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-moba | `skills/godot-genre-moba/SKILL.md` | present |  | blocked | net-heavy genre; cannot be honest without netcode | 2026-11-11 | blocked |  | No Bevy body. |
| godot-genre-rts | `skills/godot-genre-rts/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-tower-defense | `skills/godot-genre-tower-defense/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-metroidvania | `skills/godot-genre-metroidvania/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-open-world | `skills/godot-genre-open-world/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-roguelike | `skills/godot-genre-roguelike/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-survival | `skills/godot-genre-survival/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-card-game | `skills/godot-genre-card-game/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-educational | `skills/godot-genre-educational/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-horror | `skills/godot-genre-horror/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-puzzle | `skills/godot-genre-puzzle/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-visual-novel | `skills/godot-genre-visual-novel/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-romance | `skills/godot-genre-romance/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-battle-royale | `skills/godot-genre-battle-royale/SKILL.md` | present |  | blocked | net-heavy genre; cannot be honest without netcode | 2026-11-11 | blocked |  | No Bevy body. |
| godot-genre-idle-clicker | `skills/godot-genre-idle-clicker/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-party | `skills/godot-genre-party/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-racing | `skills/godot-genre-racing/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-rhythm | `skills/godot-genre-rhythm/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-sandbox | `skills/godot-genre-sandbox/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-simulation | `skills/godot-genre-simulation/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-sports | `skills/godot-genre-sports/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-genre-stealth | `skills/godot-genre-stealth/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | Genre router later. No stub this phase. |
| godot-ai-navigation | `skills/godot-ai-navigation/SKILL.md` | present |  | not_started |  |  | gdscript_to_rust |  | AI movement routing later. No stub this phase. |
