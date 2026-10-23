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
  - Local Guest Profile UI: displays a placeholder profile with a default Steve avatar and offline status indicator (does not represent an authenticated Minecraft account).
- **Microsoft Authentication Pipeline (Staged):**
  - Microsoft OAuth 2.0 Device Code Flow client implementation.
  - Integration with Xbox Live and XSTS token exchange routines.
  - Minecraft Services API integration staged (currently returns HTTP 403; Application ID review status: Not Yet Submitted).
- **Windows Bootstrapper & Distribution:**
  - Automated desktop installer/bootstrapper utility for Windows 10/11 environments (`luxury-bootstrapper.exe`).
  - Desktop shortcut creation with official crystal feather iconography.
- **Client Mod & HUD Integration (Private Community Build):**
  - Lightweight in-game HUD modules (FPS display, XYZ coordinates, and Keystrokes visualizer).
  - Performance and utility modules (memory cleaner routine and gamma fullbright).

---

*Note: LUXURY Launcher is a private, non-commercial software project for a closed community of approximately 50 players. Source code is maintained in private repositories.*
