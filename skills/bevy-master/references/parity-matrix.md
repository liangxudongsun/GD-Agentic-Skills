# Parity matrix (living)

Phase-1 seed only; remainder not_started pending next pass.

Schema lock stays in Forge. This file is the product copy agents load with `bevy-master`. Godot is source of truth. No Bevy skill without a Godot counterpart or an explicit new-engine need. Phase-1 has no new-engine-only skills.

`blocked` / `revisit` / `n_a_godot_only` / `parked` require `blocker` and `revisit_after`.

`script_port`: `n/a` | `gdscript_to_rust` | `python_to_rust` | `keep_python_tooling` | `blocked`.

`docs_mapped` means docs were checked and linked. It is not a port.

Columns: skill_id, godot_path, godot_status, bevy_path, bevy_status, blocker, revisit_after, script_port, docs_refs, notes.

| skill_id | godot_path | godot_status | bevy_path | bevy_status | blocker | revisit_after | script_port | docs_refs | notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| godot-master | `skills/godot-master/SKILL.md` | present | `skills/bevy-master/SKILL.md` | docs_mapped | | | n/a | https://docs.rs/bevy/latest/bevy/ https://bevy.org/learn/quick-start/getting-started/ecs/ | Greenlit 2026-10-11. Phase-1 hub scaffold. Not a second master over Godot. Bevy 0.20.0. docs.rs links use `latest`. |
| godot-project-foundations | `skills/godot-project-foundations/SKILL.md` | present | | not_started | | | n/a | | Feature folders and naming. No stub this phase. |
| godot-composition | `skills/godot-composition/SKILL.md` | present | | not_started | | | gdscript_to_rust | | Godot composition is not Bevy ECS. A later row must teach bundles and systems. |
| godot-signal-architecture | `skills/godot-signal-architecture/SKILL.md` | present | | not_started | | | gdscript_to_rust | | Map to Bevy messages, events, or observers only after the docs pin. No stub yet. |
| godot-resource-data-patterns | `skills/godot-resource-data-patterns/SKILL.md` | present | | not_started | | | gdscript_to_rust | | Data as components and resources. No `.tres` twin. |
| godot-state-machine-advanced | `skills/godot-state-machine-advanced/SKILL.md` | present | | not_started | | | gdscript_to_rust | | States as components or enums plus systems. No stub yet. |
| godot-gdscript-mastery | `skills/godot-gdscript-mastery/SKILL.md` | present | | n_a_godot_only | language skill; Bevy gameplay runtime is Rust | after-bevy-0.x-rust-skill | n/a | | No Bevy body. |
| godot-version-migration | `skills/godot-version-migration/SKILL.md` | present | | n_a_godot_only | Godot hop history | after-bevy-version-hub | n/a | | No Bevy body. A Bevy version hub is a later explicit new-engine need, not this row. |
| godot-characterbody-2d | `skills/godot-characterbody-2d/SKILL.md` | present | `skills/bevy-character-movement/SKILL.md` | docs_mapped | | | gdscript_to_rust | https://bevy.org/learn/quick-start/getting-started/ecs/ https://docs.rs/bevy/latest/bevy/time/index.html | Phase-1 starter. Docs-first. Coyote time and jump buffer are design notes, not a Node port. |
| godot-physics-3d | `skills/godot-physics-3d/SKILL.md` | present | `skills/bevy-physics-3d/SKILL.md` | docs_mapped | | | gdscript_to_rust | https://docs.rs/bevy/latest/bevy/ https://bevy.org/learn/quick-start/getting-started/plugins/ | Phase-1 starter. Docs-first. Do not pretend Jolt, PhysicalBone, or Joint3D APIs exist in Bevy. |
| godot-2d-physics | `skills/godot-2d-physics/SKILL.md` | present | | not_started | | | gdscript_to_rust | | Startable later. Not a Phase-1 stub. |
| godot-multiplayer-networking | `skills/godot-multiplayer-networking/SKILL.md` | present | | blocked | networking ownership not opened; no Bevy netcode choice yet | 2026-11-11 | blocked | | No Bevy body. |
| godot-server-architecture | `skills/godot-server-architecture/SKILL.md` | present | | blocked | same networking hold as multiplayer | 2026-11-11 | blocked | | No Bevy body. |
| godot-agent-vision | `skills/godot-agent-vision/SKILL.md` | present | | not_started | | | keep_python_tooling | | Host capture may stay Python. Do not stub a twin. |
| godot-monte-carlo-balancer | `skills/godot-monte-carlo-balancer/SKILL.md` | present | | not_started | | | keep_python_tooling | | Existing Rust lab is Godot-side. Not a Bevy port. |
| godot-builder | `skills/godot-builder/SKILL.md` | present | | n_a_godot_only | Godot CLI / headless editor | after-bevy-cli-proven | n/a | | No twin until a Bevy CLI need is proven. |
| godot-analyst | `skills/godot-analyst/SKILL.md` | present | | n_a_godot_only | Godot project audit (ResourceLoader, scene graph) | after-bevy-audit-need | n/a | | No twin until proven. |
| godot-auditor | `skills/godot-auditor/SKILL.md` | present | | n_a_godot_only | Godot never-list / ObjectDB | after-bevy-audit-need | n/a | | No twin until proven. |
