---
name: bevy-testing-patterns
description: "Docs-first stub for Cargo tests around Bevy work. Godot counterpart: godot-testing-patterns. Not a GdUnit port. Keywords: Bevy, cargo test, Rust, libtest."
---

# Bevy testing patterns (docs-first stub)

Not a full port. Tests here are Cargo's test harness. There is no GdUnit twin.

## When to use

Load this when a Bevy crate needs unit or integration tests. The Cargo book page for `cargo test` (opened 2026-10-11) is the source. A current Bevy "how to `App::update` inside `#[test]`" page was not opened, so that recipe stays a gap.

## ECS shape

- **Command:** `cargo test` compiles and runs unit tests, integration tests, and documentation tests. `cargo test name_filter` runs names that contain the filter. Arguments after `--` go to libtest (`cargo test -- --help`).
- **What runs:** functions annotated with `#[test]`. The harness runs them in multiple threads. The working directory for each test is the package root, so relative paths resolve from that root no matter where you invoked Cargo.
- **Scope:** default `cargo test` covers the lib, bins as unit tests, integration tests, and doc tests, and it builds examples. `--lib` limits to the library. `harness = false` on a target means you supply `main`.
- **Profile:** the `test` profile is the default. `--profile=debug` keeps debug info. `-- --no-capture` shows test output.
- **Bevy types inside a test:** not specified here. Do not copy an `App::new()` test from an old discussion. Bevy's own crates contain `#[cfg(test)]` modules; their helpers were not opened as a public guide.

## Godot idea to Bevy idiom

| Idea | Bevy idiom (idea only) |
| --- | --- |
| Run the suite | `cargo test` from the package |
| One test name | `cargo test name_filter` |
| See prints | `cargo test -- --no-capture` |
| Scene-tree test runner | No twin. GdUnit stays on the Godot skill |

## Gaps

- No docs.rs `latest` page was opened that shows `App`, `MinimalPlugins`, and `app.update()` inside `#[test]`. Do not invent that harness.
- Headless frame capture, golden images, and input injection for tests were not opened.
- Doctest working-directory rules differ from unit tests (workspace root for `rustdoc` compile). Do not assume a doctest can read `assets/` the same way.

## NEVER

- No GdUnit, GUT, or Godot test-runner types.
- No `App::update` test recipe this file did not open.
- No third-party Bevy test crates.
- No Creation Station content.
- No umbrella skill over Godot and Bevy.
- Do not mark this row `ported`. It is `docs_mapped`.

## Reference

docs.rs links use the unversioned `latest` permalink. The library pin on bevy-master stays **0.20.0**.

### Official Documentation
- [Migration guides](https://bevy.org/learn/migration-guides/introduction/)  -  Unversioned hop index.
- [bevy crate](https://docs.rs/bevy/latest/bevy/)  -  Unversioned API index.
- [cargo test](https://doc.rust-lang.org/cargo/commands/cargo-test.html)  -  `#[test]`, filters, libtest args, package root as cwd.
- [Examples](https://github.com/bevyengine/bevy/tree/latest/examples#examples)  -  Example tree on the `latest` branch. Examples are not the test harness.

### Related Skills

#### Prerequisites
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Who owns which piece of state.
- [bevy-project-foundations](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-project-foundations/SKILL.md)  -  The Cargo package `cargo test` runs against.

#### Complements
- [godot-testing-patterns](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/godot-testing-patterns/SKILL.md)  -  Godot counterpart. GdUnit stays there.

#### Downstream / consumers
- None yet.

#### Master
- [bevy-master](https://github.com/thedivergentai/gd-agentic-skills/blob/main/skills/bevy-master/SKILL.md)  -  Bevy router.
