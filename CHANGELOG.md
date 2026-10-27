# Changelog — LUXURY Launcher

All notable changes to the **LUXURY Launcher** project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [4.8.0] — 2026-10-22

### Added
- **Target Minecraft 1.21.11 Compatibility:**
  - Automated download and cryptographic SHA-1 verification pipeline for official Mojang release files.
  - Integration with Fabric Loader `0.19.5` and Fabric API `0.141.6+1.21.11`.
  - Java 21 LTS runtime orchestration with optimized JVM garbage collection parameters (`-XX:+UseG1GC`).
- **Desktop Launcher (Tauri 2 + Rust + React):**
  - Cosmic deep-space visual theme with cyan accents, translucent glassmorphism cards, and custom controls.
  - Native Windows title bar controls (Minimize, Maximize/Restore, Close) integrated with Tauri 2 desktop window management.
  - Real-time TCP ping monitor for community and favorite servers (displaying online status and latency).
  - Launcher settings for JVM memory allocation (minimum/maximum RAM limits) and custom execution arguments.
  - Centralized, structured installation target at `%APPDATA%\Launcheres\Clientes\LuxuryClient\`.
- **User Interface & Profile Display:**
  - Local Guest Profile UI: displays a placeholder profile with a default Steve avatar and offline status indicator (strictly visual; does not represent an authenticated account and cannot launch Minecraft or connect to servers without an authenticated account and a valid license).
- **Microsoft Authentication & Minecraft Services:**
  - Application ID Review: officially approved and allowlisted by Minecraft Services on October 26, 2026 (`MCENotify@microsoft.com`).
  - Microsoft OAuth 2.0 Device Code Flow, Xbox Live, and XSTS token pipeline successfully tested in live end-to-end authentication.
  - Minecraft Services authentication (`login_with_xbox`) and official player profile retrieval (`/minecraft/profile`) successfully tested; historical HTTP 403 restriction resolved.
  - Live game launch of Minecraft Java Edition 1.21.11 with Fabric Loader successfully executed with verified Microsoft session tokens, connecting to multiplayer community servers.
  - Mandatory pre-launch session and game ownership verification calling `/entitlements/mcstore` and `/minecraft/profile` implemented in backend; additional negative-case testing for unlicensed accounts pending.
  - Automated session refresh on token expiration implemented and verified in pre-launch sequence.
  - Windows DPAPI token encryption and structural validation for local accounts (`accounts.json`), safely rejecting corrupt or manipulated profiles.
- **Windows Bootstrapper & Distribution:**
  - Automated desktop installer/bootstrapper utility for Windows 10/11 environments (`luxury-bootstrapper.exe`).
  - Desktop shortcut creation with official crystal feather iconography.
- **Client Mod & HUD Integration (Private Community Build):**
  - Lightweight in-game HUD modules (FPS display, XYZ coordinates, and Keystrokes visualizer).
  - Performance and utility modules (memory cleaner routine and gamma fullbright).

---

*Note: LUXURY Launcher is a private, non-commercial software project for a closed community of approximately 50 players. Source code is maintained in private repositories.*
