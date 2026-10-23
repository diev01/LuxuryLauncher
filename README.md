<p align="center">
  <img src="assets/luxury-logo.png" alt="LUXURY Launcher Logo" width="130" />
</p>

<h1 align="center">LUXURY Launcher</h1>

<p align="center">
  <strong>A modern, custom Minecraft Java Edition launcher designed for a private community.</strong>
</p>

<p align="center">
  <a href="#project-status"><img src="https://img.shields.io/badge/Version-4.8.0-00e5ff.svg?style=flat-square" alt="Version 4.8.0" /></a>
  <a href="#project-status"><img src="https://img.shields.io/badge/Status-Active%20Development-38bdf8.svg?style=flat-square" alt="Active Development" /></a>
  <a href="#project-status"><img src="https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011-0ea5e9.svg?style=flat-square" alt="Platform Windows" /></a>
  <a href="#project-status"><img src="https://img.shields.io/badge/Minecraft-1.21.11-0284c7.svg?style=flat-square" alt="Minecraft 1.21.11" /></a>
  <a href="#project-status"><img src="https://img.shields.io/badge/Mod%20Loader-Fabric-0369a1.svg?style=flat-square" alt="Mod Loader Fabric" /></a>
  <a href="#project-status"><img src="https://img.shields.io/badge/Source%20Code-Private-64748b.svg?style=flat-square" alt="Source Code Private" /></a>
</p>

---

## Overview

**LUXURY Launcher** is a custom Minecraft Java Edition launcher for Windows, designed to provide a modern and streamlined experience for a private community of approximately 50 players.

It is an independent software project, currently in active development, created to deliver a tailored Minecraft experience powered by the Fabric mod loader. LUXURY Launcher focuses on clean desktop performance, an intuitive cosmic-inspired aesthetic, and straightforward client management for friends and private community members.

> [!NOTE]
> This repository is exclusively informational and serves as the official landing page and project reference for the Minecraft Services Application ID review. Source code is maintained privately and is not distributed as an open-source project.

---

## About the Project

LUXURY Launcher was built to simplify how our private community connects, launches, and enjoys Minecraft Java Edition with Fabric optimizations.

Key highlights include:
- **Dedicated Java Launcher:** Tailored specifically for Minecraft Java Edition.
- **Modern Dark & Cyan Interface:** Clean dark aesthetic with glassmorphic cards and vibrant cyan accents.
- **Fabric Mod Loader Integration:** Direct orchestration of Fabric Loader and runtime configurations for Minecraft Java 1.21.11.
- **Client File Installation & Management:** Automated deployment and integrity verification of game instances and libraries.
- **Tailored for Private Use:** Crafted exclusively for an invitation-only group of approximately 50 players, rather than broad public commercial release.

---

## Technologies Used

The desktop client is developed with a modern native desktop stack:

| Component | Technology | Role |
| :--- | :--- | :--- |
| **Desktop Framework** | [Tauri 2](https://tauri.app/) | Secure, lightweight native Windows windowing and system layer |
| **Core Backend** | [Rust](https://www.rust-lang.org/) | File management, network calls, SHA-1 verification, and process execution |
| **Frontend UI** | [React 18](https://react.dev/) + [TypeScript](https://www.typescriptlang.org/) | High-performance reactive user interface |
| **Styling** | [Tailwind CSS](https://tailwindcss.com/) | Dark cosmic aesthetic with custom cyan accents |
| **Web Runtime** | Microsoft Edge WebView2 | Native Windows web rendering engine |
| **Game Runtime** | Java 21 LTS | High-performance execution runtime for Minecraft 1.21.11 |
| **Mod Loader** | [Fabric](https://fabricmc.net/) | Lightweight, modular modding framework |

---

## Verified Features

The following features are implemented and functioning in the current build (`4.8.0`):

- **Modern Desktop Interface:** Responsive cosmic dark-space UI with custom cyan highlights, stylized title bar, and native Windows window controls (Minimize, Maximize/Restore, Close).
- **Local Guest Profile UI:** Displays a local placeholder profile with a default Steve avatar and offline status indicator. This feature does not represent an authenticated Minecraft account.
- **Client File Installation System:** Automated file extraction, cryptographic SHA-1 verification of official assets and libraries, and deployment to a structured installation path (`%APPDATA%\Launcheres\Clientes\LuxuryClient\`).
- **Fabric Integration:** Integration with Fabric Loader `0.19.5` and Fabric API `0.141.6+1.21.11`.
- **Launcher & JVM Settings:** User-configurable RAM allocation limits (minimum/maximum memory), JVM garbage collection tuning flags (`-XX:+UseG1GC`), and custom resolution options.
- **Windows Installer / Bootstrapper:** Dedicated lightweight Windows installer utility (`luxury-bootstrapper.exe`) that configures the client directory and generates official desktop shortcuts.
- **Community Server Monitoring:** Real-time TCP ping utility providing live reachability and latency metrics for community servers.
- **Minecraft Instance Management:** Standardized instance directories with dedicated subfolders for mods, assets, configs, and runtime logs.

> [!IMPORTANT]
> The automated update delivery system is currently in development and staging. It is not yet marked as fully released.

---

## Development Roadmap

For full details on feature progress, see [ROADMAP.md](ROADMAP.md).

| Feature / Milestone | Category | Status |
| :--- | :--- | :---: |
| **Tauri 2 + Rust Core Architecture** | Desktop Core | 🟢 Completed |
| **Modern React + Cyan Visual Design** | Frontend UI | 🟢 Completed |
| **Local Guest Profile UI** | User Interface | 🟢 Completed |
| **Minecraft 1.21.11 & Fabric Setup** | Runtime Integration | 🟢 Completed |
| **Windows Bootstrapper Utility** | Installation | 🟢 Completed |
| **TCP Community Server Monitor** | Network | 🟢 Completed |
| **Microsoft OAuth 2.0 (Device Code Flow)** | Authentication | 🟡 In Development |
| **Minecraft Services Integration** | Services | 🟡 In Development |
| **Minecraft Java Ownership Verification** | Security & Compliance | 🟡 In Development |
| **Full Authenticated Game Launch** | Core Gameplay | 🟡 In Development |
| **Launcher Performance & Footprint Optimization** | Optimization | 🟡 In Development |
| **Launcher Update Delivery Pipeline** | Distribution | 🟡 In Development |
| **User Experience Improvements** | UI / UX | 🟡 In Development |
| **Minecraft Instance Management Enhancements** | Game Management | 🟡 In Development |
| **Bug Fixes and Stability Testing** | Quality Assurance | 🟡 In Development |
| **Multi-Account Switching** | Authentication | 🔵 Planned |
| **Automated Resource Pack Synchronizer** | Private Community | 🔵 Planned |

---

## Microsoft Authentication & Minecraft Services Status

LUXURY Launcher is actively developing official authentication to ensure compliance with Microsoft and Mojang standards.

### Current Implementation State

- **Microsoft OAuth 2.0 (Device Code Flow):** Partially implemented. The client successfully requests device authorization codes from `https://login.microsoftonline.com/consumers/oauth2/v2.0/devicecode` and handles polling routines.
- **Xbox Live & XSTS Integration:** The token exchange pipeline for Xbox Live user tokens and XSTS security tokens (`rp://api.minecraftservices.com/`) is integrated.
- **Minecraft Services Status (HTTP 403):** Minecraft Services (`api.minecraftservices.com/authentication/login_with_xbox`) currently returns **HTTP 403 Forbidden** (*Invalid app registration*). This response is expected while the Application ID is pending official allowlisting and approval.
- **Application ID Review:** Official approval of the Application ID is currently **pending review** with Minecraft Services.
- **Full Authentication Availability:** Complete Microsoft Java Edition authentication is **not yet available** in the public build while approval is pending.
- **Game Ownership Verification:** Verification of legitimate game licenses (via `/entitlements/mcstore`) is implemented structurally in the pipeline, but remains **pending live end-to-end validation** until the Application ID is approved.
- **Security & Privacy:** Authentication strictly adheres to the Microsoft Identity Platform guidelines. All tokens remain stored locally on the user's machine; no credentials or tokens are ever proxied, collected, or transmitted to external servers.

---

## Intended Audience

- **Target Audience:** A closed, private community of approximately **50 players** (friends and community members).
- **Non-Commercial Nature:** LUXURY Launcher is not intended for commercial release, public mass distribution, sale, or subscription.
- **No Monetization:** The launcher contains no paywalls, microtransactions, or paid access of any kind.

---

## Project Status

| Metric | Details |
| :--- | :--- |
| **Project Name** | LUXURY Launcher |
| **Current Version** | `4.8.0` |
| **Development Status** | Active Development |
| **Operating System** | Windows 10 / Windows 11 (64-bit) |
| **Target Game** | Minecraft Java Edition |
| **Target Game Version** | `1.21.11` |
| **Modding Framework** | Fabric Loader (`0.19.5`) |
| **Java Runtime** | Java 21 LTS |
| **Source Code** | Private (Proprietary / Closed) |
| **Audience Scope** | Private Community (~50 users) |

---

## Disclaimer

**LUXURY Launcher** is an independent, non-official project and is **not affiliated with, endorsed by, sponsored by, or approved by Mojang Studios, Microsoft Corporation, or any of their affiliates or subsidiaries**.

- **Minecraft** is a registered trademark of Mojang Synergies AB.
- All trademarks, registered trademarks, product names, logos, and brands mentioned in this project are the property of their respective owners.
- LUXURY Launcher requires a legitimate copy of Minecraft Java Edition purchased from official channels.
