# Troubleshooting Index

**Author:** Aarav Arora  
**System:** MacBook Pro (13-inch, 2019, Apple T2 Security Chip)  

---

## 1. Purpose

This directory contains all major issues encountered during the Ubuntu 24.04 LTS dual-boot installation and the verified resolutions.  
Each file follows a **problem → cause → resolution → verification** format to ensure clarity and reproducibility.

---

## 2. Documented Issues

| File | Issue | Status |
|------|--------|--------|
| `SIP_Issue_and_Resolution.md` | SIP prevented rEFInd EFI install | ✅ Resolved |
| `SecureBoot_Configuration_Error.md` | macOS firmware blocked external USB boot | ✅ Resolved |
| `USB_Not_Detected.md` | Etcher-flashed Ubuntu USB not showing in Startup Manager | ✅ Resolved |
| `T2_Keyboard_Trackpad_Fix.md` | Keyboard/trackpad not working in Ubuntu post-install | ✅ Resolved |
| `rEFInd_BootOrder_Reset.md` | Ubuntu GRUB overwrote EFI boot priority | ✅ Resolved |

---

## 3. Troubleshooting Workflow

1. **Identify and document symptoms** (error messages, screenshots).  
2. **Search and validate fixes** from official docs and trusted community sources.  
3. **Test solution in controlled steps.**  
4. **Capture before/after evidence.**  
5. **Document commands, reasoning, and outcomes.**

---

## 4. System Logs Reference

All verification evidence (terminal outputs, screenshots, and config files) is preserved in `/Screenshots` and `/Resources` for audit and reproducibility.

---

**Status:** All known issues from Ubuntu installation phase resolved.  
**Next Update:** Add kernel update driver-breakage logs (if they occur during Week 2 testing).
