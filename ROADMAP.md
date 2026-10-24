# Development Roadmap — LUXURY Launcher

This document outlines the milestones, current development status, and planned roadmap for **LUXURY Launcher**.

LUXURY Launcher is developed as a non-commercial, custom Minecraft Java Edition launcher for a private community of approximately 50 players.

---

## 🗺️ Status Legend

| Status | Meaning |
| :---: | :--- |
| 🟢 **Completed** | Feature is implemented and verified in the current build (`4.8.0`). |
| 🟡 **In Development** | Feature is actively being developed, integrated, or awaiting external review/evaluation. |
| ⚪ **Submitted (Awaiting Review)** | The official review application has been submitted to Minecraft Services and is awaiting evaluation. |
| 🔵 **Planned** | Feature is scheduled for future milestones. |

---

## 📌 Feature Breakdown

### 1. Authentication & Account Management

| Feature | Status | Notes |
| :--- | :---: | :--- |
| **Local Guest Profile UI** | 🟢 Completed | Displays a local placeholder profile with a default Steve avatar and offline status indicator. Strictly visual; does not allow launching Minecraft or accessing servers without an authenticated account and a valid license. |
| **Application ID Review** | ⚪ Submitted (Awaiting Review) | Status: **Application ID Review — Submitted (Awaiting Review)**. The official Minecraft Services Application ID review form has been submitted. The application is currently awaiting evaluation by Microsoft/Mojang. Approval is not guaranteed. |
| **Microsoft OAuth 2.0 (Device Code Flow)** | 🟡 In Development | Partially implemented in code and in active development; complete end-to-end testing remains pending external service authorization. |
| **Xbox Live & XSTS Token Flow** | 🟡 In Development | Token acquisition routines integrated in backend; complete end-to-end testing with Minecraft Services remains pending. |
| **Minecraft Services Integration** | 🟡 In Development | Minecraft Services currently returns HTTP 403 Forbidden ('Invalid app registration') when the launcher attempts to authenticate. An Application ID review has been submitted to request authorization. The exact resolution remains subject to Microsoft/Mojang's evaluation. |
| **Minecraft Java Ownership Verification** | 🟡 In Development | License verification logic (`/entitlements/mcstore` and `/minecraft/profile`) implemented in backend code according to current architecture; full end-to-end testing remains pending. |
| **Full Authenticated Game Launch** | 🟡 In Development | Pre-launch checks in code require an authenticated Microsoft account and verified ownership; complete testing of authenticated launch remains pending resolution of Minecraft Services authentication. |
| **Multi-Account Switching** | 🔵 Planned | Safe profile switching between authorized Microsoft accounts. |

---

### 2. Desktop Launcher & User Experience

| Feature | Status | Notes |
| :--- | :---: | :--- |
| **Modern Desktop Shell** | 🟢 Completed | Built with Tauri 2, Rust, React 18, and Tailwind CSS. |
| **Cosmic & Cyan UI Theme** | 🟢 Completed | Custom glassmorphism cards, cosmic background, and custom UI components. |
| **Native Windows Title Bar Controls** | 🟢 Completed | Custom minimize, maximize/restore, and close buttons integrated with Tauri. |
| **Windows Bootstrapper / Installer** | 🟢 Completed | Automatic directory setup and desktop shortcut configuration (`luxury-bootstrapper.exe`). |
| **User Experience Improvements** | 🟡 In Development | Ongoing refinement of setup guidance and client interface responsiveness. |
| **Accessibility & Theme Customization** | 🔵 Planned | UI scaling options and enhanced contrast modes. |

---

### 3. Game Management & Mod Loader

| Feature | Status | Notes |
| :--- | :---: | :--- |
| **Minecraft Java 1.21.11 Target** | 🟢 Completed | Official version manifest parsing and asset integrity verification. |
| **Fabric Loader & Fabric API Integration** | 🟢 Completed | Automatic Fabric Loader runtime resolution for Java 21 LTS. |
| **JVM Memory & Argument Settings** | 🟢 Completed | User-configurable RAM allocation limits and optimized GC flags (`-XX:+UseG1GC`). |
| **TCP Community Server Monitor** | 🟢 Completed | Real-time TCP ping and latency display for community servers. |
| **Minecraft Instance Management Enhancements** | 🟡 In Development | Structured directory isolation and instance recovery routines. |
| **Automated Resource Pack Synchronizer** | 🔵 Planned | Automated private community asset updates without manual file transfers. |

---

### 4. Performance, Updates & Stability

| Feature | Status | Notes |
| :--- | :---: | :--- |
| **Launcher Performance & Footprint Optimization** | 🟡 In Development | Ongoing profiling to minimize CPU and RAM footprint on Windows. |
| **Launcher Update Delivery Pipeline** | 🟡 In Development | Staged updater infrastructure to deliver verified client releases safely. |
| **Bug Fixes and Stability Testing** | 🟡 In Development | Continuous testing across Windows 10 and Windows 11 environments. |
| **Automated Crash Diagnostics** | 🔵 Planned | Safe client error reporting for launcher troubleshooting. |

---

## 🔒 Compliance & Standards

As part of the roadmap toward completing Microsoft Authentication and Minecraft Services integration:

1. **Official Microsoft Identity**: The launcher implements standard Microsoft OAuth 2.0 mechanisms rather than scraping or insecure credential entry.
2. **Game Ownership Mandate**: Players must possess an official, valid Minecraft Java Edition license. The launcher does not bypass license validation.
3. **Privacy & Token Handling**: Authentication tokens are handled locally and transmitted to the official Microsoft, Xbox Live, and Minecraft Services endpoints as required for authentication. LUXURY Launcher does not operate an independent authentication server or intentionally transmit user credentials or tokens to unrelated third-party services. Full authentication and security validation remain in progress.
