# Development Roadmap — Luxury Launcher

This document outlines the milestones, current development status, and planned roadmap for **Luxury Launcher**.

Luxury Launcher is developed as a non-commercial, custom Minecraft Java Edition launcher for a private community of approximately 50 players.

---

## 🗺️ Status Legend

| Status | Meaning |
| :---: | :--- |
| 🟢 **Completed** | Feature is implemented and verified in the current build (`4.8.0`). |
| 🟡 **In Development** | Feature is actively being developed, integrated, or awaiting external approvals. |
| 🔵 **Planned** | Feature is scheduled for future milestones. |

---

## 📌 Feature Breakdown

### 1. Authentication & Account Management

| Feature | Status | Notes |
| :--- | :---: | :--- |
| **Visual Guest Profile ("Sin conexión")** | 🟢 Completed | Clean UI state with Steve avatar and "Sin conexión" indicator. Exclusively visual; **strictly prohibited from launching Minecraft or joining servers**. |
| **Microsoft OAuth 2.0 Device Code Flow** | 🟡 In Development | OAuth flow implemented; awaiting official Minecraft Services Application ID review. |
| **Xbox Live & XSTS Token Flow** | 🟡 In Development | Token exchange pipeline ready for live endpoint verification. |
| **Minecraft Services Integration** | 🟡 In Development | Pending Application ID approval from Microsoft / Minecraft Services. |
| **Minecraft Java Ownership Verification** | 🟡 In Development | Entitlement validation (`/entitlements/mcstore`) to enforce game license requirements before game launch. |
| **Authenticated Game Launching** | 🟡 In Development | Launching is strictly gated behind verified Microsoft authentication and license checks; cannot be used until App ID approval is granted. |
| **Multi-Account Switching** | 🔵 Planned | Safe profile switching between authorized Microsoft accounts. |

---

### 2. Desktop Launcher & User Experience

| Feature | Status | Notes |
| :--- | :---: | :--- |
| **Modern Desktop Shell** | 🟢 Completed | Built with Tauri 2, Rust, React 18, and Tailwind CSS. |
| **Cosmic & Cyan UI Theme** | 🟢 Completed | Custom glassmorphism cards, cosmic background, and custom UI components. |
| **Native Windows Title Bar Controls** | 🟢 Completed | Custom minimize, maximize/restore, and close buttons integrated with Tauri. |
| **Windows Bootstrapper / Installer** | 🟢 Completed | Automatic directory setup and desktop shortcut configuration. |
| **User Experience & Onboarding Improvements** | 🟡 In Development | Streamlined setup wizard and first-time configuration guidance. |
| **Accessibility & Theme Tweaks** | 🔵 Planned | Contrast adjustments and customizable UI scaling. |

---

### 3. Game Management & Mod Loader

| Feature | Status | Notes |
| :--- | :---: | :--- |
| **Minecraft Java 1.21.11 Target** | 🟢 Completed | Official version manifest parsing and asset integrity verification. |
| **Fabric Loader & Fabric API Integration** | 🟢 Completed | Automatic Fabric Loader runtime resolution for Java 21 LTS. |
| **JVM Memory & Argument Settings** | 🟢 Completed | User-configurable RAM allocation limits and optimized GC flags. |
| **TCP Community Server Monitor** | 🟢 Completed | Real-time TCP ping and latency display for community servers. |
| **Minecraft Instance Management** | 🟡 In Development | Enhanced directory isolation and clean instance recovery. |
| **Modpack & Resource Pack Synchronizer** | 🔵 Planned | Automated private community asset updates without manual file transfers. |

---

### 4. Performance, Updates & Stability

| Feature | Status | Notes |
| :--- | :---: | :--- |
| **Launcher Resource Footprint Optimization** | 🟡 In Development | Continuous profiling to maintain minimal memory and CPU usage on Windows. |
| **Launcher Update Delivery Pipeline** | 🟡 In Development | Staged updater infrastructure to deliver verified client releases safely. |
| **Bug Fixes & Stability Improvements** | 🟡 In Development | Ongoing testing across Windows 10 and Windows 11 environments. |
| **Automated Crash Diagnostics** | 🔵 Planned | Safe client error reporting for launcher troubleshooting. |

---

## 🔒 Compliance & Standards

As part of the roadmap toward completing Microsoft Authentication and Minecraft Services integration:

1. **Official Microsoft Identity**: The launcher implements standard Microsoft OAuth 2.0 mechanisms rather than scraping or insecure credential entry.
2. **Game Ownership Mandate**: Players must possess an official, valid Minecraft Java Edition license. The launcher does not bypass license validation.
3. **Privacy First**: No telemetry, analytics, personal credentials, or session tokens are collected or transmitted to external servers. All authentication tokens remain stored securely on the local machine.
