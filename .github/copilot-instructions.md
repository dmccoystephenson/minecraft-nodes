# Copilot Instructions

This repository follows the DPC (Dans Plugins Community) conventions defined at
https://github.com/Dans-Plugins/dpc-conventions. Read those conventions before
making any changes.

## Technology Stack

- Language: Kotlin
- Build tool: Gradle (Kotlin DSL)
- Target platform: Paper (Minecraft plugin, 1.21+)
- Test framework: JUnit 5
- Java version: 21

## Project Structure

```
minecraft-nodes/
 ├─ nodes/                          – Main Nodes server plugin
 │   ├─ src/main/kotlin/phonon/nodes/  – Plugin source code
 │   │   ├─ commands/               – Command executor classes
 │   │   ├─ constants/              – Enums and constant values
 │   │   ├─ war/                    – War system (attacks, treaties, alliances)
 │   │   └─ chat/                   – Chat channel system
 │   └─ src/main/resources/         – plugin.yml and config.yml
 └─ dynmap/                         – Dynmap viewer/editor (Node.js + Rust/WASM)
```

## Coding Conventions

- Follow the existing `phonon.nodes` package structure when adding new classes.
- All command executors live in `phonon/nodes/commands/`; each command gets its own file.
- Use Kotlin idioms (data classes, sealed classes, extension functions) consistently with existing code.
- The plugin relies on an external Kotlin runtime plugin; do not bundle the Kotlin stdlib in the output JAR.
- The `nodes/` subdirectory contains a self-contained Gradle project with its own `gradlew`.

## Contribution Workflow

- Branch from `develop` for all changes.
- Open a pull request against `develop`, not `main`.
- Reference the related GitHub issue in every pull request description.
