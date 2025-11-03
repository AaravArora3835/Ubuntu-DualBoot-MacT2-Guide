# Resources Directory Overview

**Author:** Aarav Arora  
**System:** MacBook Pro (13-inch, 2019, Apple T2 Security Chip)  

---

## 1. Purpose

This folder documents every technical reference, validation log, and verification record used throughout the **Ubuntu 24.04 LTS dual-boot installation** process.  

Its primary purpose is to ensure **traceability, auditability, and reproducibility** — key pillars of cybersecurity-grade documentation. Each Markdown file serves as a self-contained, timestamped record of an individual configuration phase.

---

## 2. File Index

| File | Description |
|------|--------------|
| `Hardware_Specs.md` | Full hardware profile of the MacBook Pro (CPU, storage, firmware). |
| `Firmware_Settings_Notes.md` | Complete log of firmware modifications (Secure Boot, SIP, rEFInd). |
| `Checksums_And_Verification.md` | ISO integrity validation and checksum comparison logs. |
| `Toolkit_Downloads.md` | List of verified tools, drivers, and installers used pre- and post-setup. |
| `Resources_Overview.md` | (This file) Directory-level summary and purpose statement. |

---

## 3. Documentation Flow

**Phase 1 — Pre-Installation (Oct 30–31):**
- Verified Ubuntu ISO SHA-256 checksum.  
- Configured Secure Boot and SIP settings.  
- Installed rEFInd Boot Manager for EFI control.  

**Phase 2 — Installation (Nov 2):**
- Executed Ubuntu dual-boot setup via “Install alongside macOS.”  
- Captured evidence of all installation steps.  
- Validated partitioning and file system allocation.  

**Phase 3 — Post-Installation (Nov 2–3):**
- Restored rEFInd as primary bootloader using `efibootmgr`.  
- Installed T2 hardware drivers (`apple-bce-dkms`).  
- Verified Wi-Fi, keyboard, and trackpad operation.  

---

## 4. Security & Verification Practices

* All downloads were obtained from **official vendor HTTPS sources**.  
* Each file’s checksum was compared against published Ubuntu or tool provider values.  
* Screenshots and terminal outputs were timestamped for validation.  
* Each configuration step was documented immediately upon execution for reproducibility.  

---

## 5. Educational Value

This `/Resources` folder is intentionally structured for **technical transparency** and **educational reuse**.  
It models professional DevSecOps documentation discipline — showing how to plan, execute, and validate a dual-boot installation securely under hardware-level constraints (Apple T2 chip).  

This structure will be mirrored in all future repositories for consistency across Aarav Arora’s cybersecurity portfolio.

---

**Repository Section Status:** ✅ Completed  
