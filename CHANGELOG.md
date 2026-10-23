# Changelog — Luxury Launcher

All notable changes to the **Luxury Launcher** project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [4.8.0] — 2026-10-22

### Added
- **Target Minecraft 1.21.11 Compatibility:**
  - Automated download and integrity verification pipeline for official Mojang release files.
  - Integration with Fabric Loader `0.19.5` and Fabric API `0.141.6+1.21.11`.
  - Java 21 LTS runtime orchestration with optimized JVM garbage collection parameters (`-XX:+UseG1GC`).
- **Desktop Launcher (Tauri 2 + Rust + React):**
  - Cosmic deep-space visual theme with cyan accents, translucent glassmorphism cards, and custom controls.
  - Native Windows title bar controls (Minimize, Maximize/Restore, Close) integrated with Tauri 2 desktop window management.
  - Real-time TCP ping monitor for community and favorite servers (displaying online status and latency).
  - Profile and memory configuration options (RAM allocation limits and custom JVM arguments).
  - Local profile selector with safe offline/guest state representation.
  - Centralized, structured installation target at `%APPDATA%\Launcheres\Clientes\LuxuryClient\`.
- **Microsoft Authentication Pipeline (Preparation & Device Code Flow):**
  - Microsoft OAuth 2.0 Device Code authentication architecture.
  - Xbox Live, XSTS token acquisition routines, and Minecraft Services endpoint structure (staged pending official Application ID approval).
- **Windows Bootstrapper & Packaging:**
  - Automated desktop installer/bootstrapper utility for Windows 10/11 environments.
  - Desktop shortcut creation with official crystal feather iconography.
- **Client Mod & HUD Integration (Private Community Build):**
  - Lightweight in-game HUD modules (FPS counter, XYZ coordinates, and Keystrokes visualizer).
  - Performance utilities (memory clean routine and gamma fullbright).

---

## [4.7.0] — 2026-09-15

### Added
- Initial desktop shell prototype using Tauri and React.
- Basic server list interface and configuration parser.
- Prototype game directory file management.

---

*Note: Luxury Launcher is a private, non-commercial software project for a closed community of players. Source code is maintained in private repositories.*
