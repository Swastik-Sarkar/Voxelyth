# Voxelyth

**A Rust-native Minecraft Java Edition 1.8.9 client.**

Voxelyth is an independent project focused on researching, understanding and eventually reimplementing Minecraft Java Edition 1.8.9 in Rust.

The project aims to provide vanilla-compatible gameplay and multiplayer connectivity while establishing a modular architecture that can support independent rendering implementations and performance optimizations.

The repository combines the research and reverse-engineering documentation with the actual Rust client implementation.

> **Current stage:** Pre-alpha — Research and Reverse Engineering.

---

## Project Structure

```text
Voxelyth/
│
├── client/                         # Main Rust client
│   ├── Cargo.toml                  # Rust package configuration
│   ├── Cargo.lock                  # Locked dependency versions
│   │
│   ├── src/                        # Application source code
│   │   └── main.rs                 # Client entry point
│   │
│   ├── crates/                     # Future modular Rust components
│   │
│   ├── game/                       # Local game/runtime directory
│   │   ├── assets/                 # Game assets
│   │   ├── resourcepacks/          # Resource packs
│   │   ├── saves/                  # Single-player worlds
│   │   ├── screenshots/            # Screenshots
│   │   ├── logs/                   # Runtime logs
│   │   └── crash-reports/          # Crash reports
│   │
│   └── tests/                      # Automated tests
│
├── minecraft-research/             # Research and reverse engineering
│   │
│   ├── docs/                       # Technical documentation
│   │   ├── architecture/           # Overall engine architecture
│   │   ├── compatibility/          # Vanilla and server compatibility
│   │   ├── engine/                  # Core game engine
│   │   ├── lifecycle/              # Application lifecycle
│   │   ├── networking/              # Networking and protocol
│   │   ├── physics/                # Physics and collision
│   │   ├── rendering/              # Graphics and rendering
│   │   ├── resources/              # Assets and resource management
│   │   └── world/                  # World and chunk management
│   │
│   ├── diagrams/                   # Architecture and execution diagrams
│   ├── notes/                      # Investigation notes
│   └── references/                 # Research references and metadata
│
├── LICENSE                         # Repository license
└── README.md                       # Project overview
```

---

## Components

### 1. Client

The `client/` directory contains the actual Rust implementation of Voxelyth.

It is intended to become a native Rust Minecraft client, independently implementing the necessary game systems and functionality.

Its responsibilities will eventually include:

- Game lifecycle and application management.
- World and chunk management.
- Entity and player systems.
- Physics and collision.
- Minecraft multiplayer networking.
- Rendering and graphics.
- Resource and asset management.
- Audio and input handling.

The `crates/` directory is reserved for future modular components as the architecture develops.

### 2. Game Runtime

The `client/game/` directory serves as the default Minecraft game instance directory.

It stores runtime data separately from the engine source code, including:

- Assets and resources.
- Resource packs.
- Single-player saves.
- Screenshots.
- Logs and crash reports.
- Runtime configuration.

The game directory is intended to be configurable rather than permanently tied to the client executable's location.

This separation will allow Voxelyth to operate independently or be launched through an external launcher, particularly the Neyro Launcher project.

**Runtime files are excluded from Git.**

### 3. Minecraft Research

The `minecraft-research/` directory contains the technical research required to understand and independently reproduce Minecraft 1.8.9.

Research is organized by subsystem rather than by arbitrary source-file groupings.

The investigation covers:

| Area | Research focus |
|---|---|
| Architecture | Engine architecture and subsystem relationships |
| Lifecycle | Startup, initialization, game loop and shutdown |
| Engine | Core gameplay systems and internal state |
| World | Chunks, blocks, biomes and lighting |
| Networking | Protocol 47, packets and synchronization |
| Rendering | OpenGL, cameras, chunk rendering and shaders |
| Physics | Player movement, collision and gravity |
| Resources | Assets, textures, resource packs and audio |
| Compatibility | Vanilla behaviour and multiplayer compatibility |

Research documents are intended to contain source references, execution flows, class relationships, data structures, runtime observations and implementation requirements.

The research workspace serves as the technical foundation for the Rust implementation.

---

## Project Objectives

The long-term objectives of Voxelyth are:

1. **Vanilla Compatibility** — Reproduce Minecraft Java Edition 1.8.9 gameplay and behaviour.
2. **Multiplayer Compatibility** — Support existing Minecraft 1.8.9 multiplayer servers through Protocol 47.
3. **Rust-Native Architecture** — Implement the client independently in Rust.
4. **Rendering Architecture** — Establish interchangeable rendering implementations.
5. **Performance** — Explore independent optimizations inspired by projects such as Sodium and OptiFine.
6. **Visual Features** — Eventually support shader pipelines and additional rendering functionality.
7. **Launcher Integration** — Allow the client to be independently launched and managed by Neyro Launcher.

These are development goals, not claims about currently implemented functionality.

---

## Development Approach

Voxelyth follows a research-first development approach.

The development process is divided into the following broad stages:

| Stage | Description |
|---|---|
| Pre-alpha | Research, reverse engineering and architectural specifications |
| Alpha | Initial Rust engine and vanilla functionality |
| Beta | Gameplay, networking and compatibility development |
| Optimization | Rendering improvements and performance work |
| Release | Stability, compatibility and distribution |

Implementation decisions will be informed by research into the original game's behaviour, rather than directly reproducing its Java class hierarchy.

---

## Technology

| Component | Technology |
|---|---|
| Primary language | Rust |
| Build system | Cargo |
| Reference implementation | Minecraft Java Edition 1.8.9 |
| Reference environment | MavenMCP 1.8.9 |
| Target multiplayer protocol | Minecraft Protocol 47 |
| Target platform | Linux initially |

Graphics, networking and other supporting libraries will be selected as their architectural requirements become clear.

---

## External Reference

The original Java reference is maintained separately in a local MavenMCP 1.8.9 workspace.

It is used for behavioural analysis, source navigation and understanding the original Minecraft client architecture.

It is not vendored into this repository.

Reverse-engineering research is intended to produce independent technical documentation and implementation specifications.

---

## Repository Scope

This repository contains:

- Voxelyth's Rust client source code.
- Research and reverse-engineering documentation.
- Architecture diagrams and technical specifications.
- Automated tests and development documentation.

Generated build artifacts, local Minecraft runtime data, game assets and external reference source files are not intended to be committed.

---

## License

See [`LICENSE`](LICENSE) for the licensing terms applicable to this repository.

The licensing status of external software, game assets and Minecraft-related reference materials remains governed by their respective owners and applicable terms.
