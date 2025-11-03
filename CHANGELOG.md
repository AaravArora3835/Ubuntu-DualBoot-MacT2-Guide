# Changelog
All notable changes to this project will be documented in this file.  
This project uses **Conventional Commits** and semantic versioning for clarity.

## [Unreleased]
- Re-enable SIP and (optionally) Secure Boot after stability verification; document exact steps and screenshots.
- Post-install hardening guide (UFW, auto-updates, fail2ban).
- GRUB/rEFInd fine-tuning notes and fallback boot testing.
- Apple T2 peripherals note: trackpad/keyboard module research and outcomes.

---

## [1.0.0] — 2025-11-02 — **Dual-boot Verified**
### Added
- Completed Ubuntu 24.04 LTS installation **alongside macOS** via rEFInd.
- `Guide.md` — end-to-end installation manual (prep → install → verify).
- `SECURITY.md` — risk tradeoffs (Secure Boot / SIP) and mitigation plan.
- Day 3 entry in `Reflection.md` with partition details, commands, and learnings.
- 13–15 installation screenshots (Startup Manager, Install Type, rEFInd menu, first boot, etc.).
### Changed
- `README.md` — added Sections: *Installation Phase*, *Verification*, *Use Cases*, *Related Projects*.
### Fixed
- Documented Wi-Fi driver workflow and network verification steps.
### Notes
- System boots both macOS and Ubuntu cleanly; rEFInd manages selection.

## [0.2.0] — 2025-10-31 — **Firmware & Media Ready**
### Added
- rEFInd boot manager installed after temporarily disabling SIP.
- USB installer created with balenaEtcher; ISO and ZIP verified (SHA-256).
- `Troubleshooting/`:
  - `SIP_Issue_and_Resolution.md`
  - `SecureBoot_Configuration_Error.md`
  - `USB_Not_Detected.md`
- Screenshots: SIP status, rEFInd install success, EFI Boot menu.
### Changed
- `Firmware_Settings_Notes.md` — Secure Boot set to **No Security**; External Boot **Allowed**.
### Notes
- Etcher and rEFInd downloads logged with sources; checksums captured.

## [0.1.0] — 2025-10-30 — **Project Initialization**
### Added
- Repository scaffold and folders (`Screenshots/`, `Resources/`, `Troubleshooting/`).
- `Hardware_Specs.md`, `Toolkit_Downloads.md`, `Checksums_And_Verification.md`.
- Disk Utility layout and Secure Boot screenshots.
### Notes
- Verified ~130 GB free for Ubuntu; planned 60–70 GB ext4 partition.

---

## Commit Convention
Use prefixes: `feat`, `fix`, `doc`, `chore`, `refactor`.  
Examples:
- `doc: add Day 3 reflection and verification screenshots`
- `fix: correct screenshot filenames to YYYY-MM-DD format`
- `chore: add repo topics and SECURITY.md`
