# Ubuntu Dual-Boot on MacBook Pro (T2 Chip) — Complete Technical Case Study

**Author:** Aarav Arora  
**Date:** November 2, 2025  
**Device:** MacBook Pro 13" (2019, Apple T2 Security Chip)  
**Status:** ✅ Fully Functional Dual-Boot Environment  

---

## Overview

This repository documents the **successful installation, configuration, and verification of Ubuntu 24.04 LTS** alongside macOS Ventura on a T2-equipped MacBook Pro.  
The project was completed as part of my cybersecurity learning roadmap to build a **native Linux environment** for hands-on security labs, penetration testing, and system administration practice.

The setup process required bypassing and later restoring Apple’s firmware-level protections — **Secure Boot** and **System Integrity Protection (SIP)** — while maintaining full data integrity and reversibility.

---

## Key Objectives

1. Create a reproducible Ubuntu installation on Apple T2 hardware.  
2. Maintain macOS functionality and data safety throughout.  
3. Implement rEFInd as a secure dual-boot manager.  
4. Document all firmware, driver, and security configurations for auditability.  
5. Demonstrate professional-grade documentation discipline aligned with cybersecurity industry standards.

---

## Technical Summary

| Category | Details |
|-----------|----------|
| **macOS Version** | Ventura 13.x |
| **Ubuntu Version** | 24.04 LTS (Noble Numbat) |
| **Boot Manager** | rEFInd 0.14.0.2 |
| **Processor** | Intel Core i5 2.4 GHz (8th Gen) |
| **Memory** | 16 GB LPDDR3 |
| **Storage** | 512 GB SSD (APFS + ext4 + EFI) |
| **Drivers Installed** | `apple-bce-dkms`, `firmware-b43-installer`, `efibootmgr` |
| **Result** | Dual-boot confirmed, Wi-Fi + keyboard + trackpad operational |

---

## Repository Structure

| Directory | Description |
|------------|--------------|
| `/Resources` | Verification logs, firmware notes, checksums, toolkit references |
| `/Screenshots` | Evidence of each installation and verification step |
| `/Troubleshooting` | Detailed issue–resolution documentation (SIP, Secure Boot, EFI, USB, T2 drivers) |
| `/Reflection.md` | Final technical and personal analysis |
| `/Guide.md` | Step-by-step reproducible installation guide |

---

## Highlights & Achievements

- **100 % integrity-verified** Ubuntu installation using SHA-256 checksums.  
- Successfully configured rEFInd to coexist with Apple’s T2 firmware.  
- Documented a **12-step reproducible install guide** with timestamped screenshots.  
- Diagnosed and resolved driver issues for Broadcom Wi-Fi and Apple Bridge Controller (apple-bce).  
- Created a **fully auditable technical report** following DevSecOps documentation standards.

---

## Educational Value

This repository models how cybersecurity students can document **system-level configuration projects** to showcase practical, verifiable skills in:

- OS hardening & bootloader management  
- Firmware security and risk assessment  
- Linux kernel module integration  
- Dual-boot and partition management  
- Documentation & traceability in secure engineering
