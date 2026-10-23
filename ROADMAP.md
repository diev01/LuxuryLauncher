# Development Roadmap — LUXURY Launcher

This document outlines the milestones, current development status, and planned roadmap for **LUXURY Launcher**.

LUXURY Launcher is developed as a non-commercial, custom Minecraft Java Edition launcher for a private community of approximately 50 players.

---

## 🗺️ Status Legend

| Status | Meaning |
| :---: | :--- |
| 🟢 **Completed** | Feature is implemented and verified in the current build (`4.8.0`). |
| 🟡 **In Development** | Feature is actively being developed, integrated, or awaiting external review/evaluation. |
| 🔵 **Planned** | Feature is scheduled for future milestones. |

---

## 📌 Feature Breakdown

### 1. Authentication & Account Management

| Feature | Status | Notes |
| :--- | :---: | :--- |
| **Local Guest Profile UI** | 🟢 Completed | Displays a local placeholder profile with a default Steve avatar and offline status indicator. This feature does not represent an authenticated Minecraft account. |
| **Application ID Review Submission** | 🟡 In Development | Status: **Not Yet Submitted**. The application form is currently being prepared for upcoming submission to Minecraft Services. |
| **Microsoft OAuth 2.0 (Device Code Flow)** | 🟡 In Development | Partially implemented; device code request and polling logic implemented, subject to future Application ID submission and review. |
| **Xbox Live & XSTS Token Flow** | 🟡 In Development | Token acquisition pipeline integrated; pending live verification with Minecraft Services. |
| **Minecraft Services Integration** | 🟡 In Development | Currently returns HTTP 403 (*Invalid app registration*). Official approval is subject to evaluation and is not guaranteed. |
| **Minecraft Java Ownership Verification** | 🟡 In Development | License verification logic (`/entitlements/mcstore`) prepared structurally; pending live end-to-end validation if approved. |
| **Full Authenticated Game Launch** | 🟡 In Development | Launching with full official Microsoft authentication is not available while Application ID review is pending submission and evaluation. |
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
3. **Privacy First**: No telemetry, analytics, personal credentials, or session tokens are collected or transmitted to external servers. All authentication tokens remain stored securely on the local machine.
