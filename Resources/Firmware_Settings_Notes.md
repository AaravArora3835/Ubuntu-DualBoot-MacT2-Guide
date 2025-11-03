# Firmware Settings Notes

**Author:** Aarav Arora  
**System:** MacBook Pro 13" (2019, Apple T2 Security Chip)  

---

## 1. Overview

This document records all firmware-level configurations made to the **MacBook Pro (2019, T2 Chip)** to enable a fully functional, secure Ubuntu 24.04 LTS dual-boot alongside macOS Ventura.  

The objective was to achieve cross-platform compatibility while maintaining reversibility, ensuring Apple firmware protections could later be restored without data loss or reinstallation.

---

## 2. Firmware Configuration Summary

| Setting | Original State | Modified State | Purpose |
|----------|----------------|----------------|----------|
| Secure Boot | Full Security | No Security | Allow unsigned bootloaders like Ubuntu GRUB |
| External Boot | Disallowed | Allowed | Permit USB boot via T2 firmware |
| SIP (System Integrity Protection) | Enabled | Disabled (temporary) | Enable EFI writing for rEFInd |
| rEFInd Boot Manager | Not Installed | Installed and verified | Enables OS selection at startup |
| Boot Order | Default (macOS only) | Reordered with `efibootmgr` | Restored rEFInd as primary EFI loader |

---

## 3. Step-by-Step Changes

### a. Disable Secure Boot and Enable External Boot
1. Boot into **macOS Recovery Mode** (hold ⌘ + R during startup).  
2. Open **Startup Security Utility**.  
3. Change settings:  
   - **Secure Boot:** No Security  
   - **External Boot:** Allow booting from external or removable media  
4. Close utility and restart macOS.

### b. Disable System Integrity Protection (SIP)
1. Boot again into macOS Recovery.  
2. Open **Utilities → Terminal**.  
3. Run:
   csrutil disable
   reboot


4. After reboot, verify in Terminal:

   ```bash
   csrutil status
   ```

   Output: `System Integrity Protection status: disabled.`

### c. Install and Configure rEFInd Boot Manager

1. Download `refind-bin-0.14.0.2.zip` from SourceForge.
2. Run installation script:

   ```bash
   ./refind-install
   ```
3. Confirm EFI folder creation at `/EFI/refind`.
4. Reboot and confirm graphical rEFInd boot menu appears.

---

## 4. Post-Installation Adjustments

After Ubuntu installation (Nov 2, 2025):

* Ubuntu replaced the EFI boot priority with GRUB.
* Restored rEFInd as primary bootloader using:

  ```bash
  sudo efibootmgr
  sudo efibootmgr -o <rEFIndID>,<UbuntuID>,<MacOSID>
  ```
* Verified both operating systems boot successfully from rEFInd.

---

## 5. Verification Evidence

| Screenshot                                           | Description                       |
| ---------------------------------------------------- | --------------------------------- |
| `/Screenshots/2025-10-30_SecureBoot_Settings.jpg`    | Secure Boot set to “No Security.” |
| `/Screenshots/2025-10-31_SIP_Status_Disabled.jpg`    | SIP disabled successfully.        |
| `/Screenshots/2025-10-31_rEFInd_Install_Success.jpg` | EFI entry added for rEFInd.       |
| `/Screenshots/2025-11-02_rEFInd_Both_OS.jpg`         | Dual-boot menu confirmed.         |
| `/Screenshots/2025-11-02_Ubuntu_First_Boot.jpg`      | Ubuntu 24.04 boot verification.   |

---

## 6. Current Status

| Setting       | Current State        | Verified |
| ------------- | -------------------- | -------- |
| Secure Boot   | Disabled             | ✅        |
| SIP           | Disabled (temporary) | ✅        |
| External Boot | Enabled              | ✅        |
| rEFInd        | Default bootloader   | ✅        |
| macOS         | Operational          | ✅        |
| Ubuntu        | Operational          | ✅        |

---

## 7. Security Recommendations

* Re-enable SIP once Ubuntu drivers (apple-bce, Wi-Fi firmware) are confirmed stable:

  ```bash
  csrutil enable
  ```
* Optionally re-enable **Medium Security** in Startup Security Utility.
* Maintain a **Time Machine** backup before future firmware changes.
* Periodically update **rEFInd** to ensure EFI compatibility with kernel updates.

---

**Status:** Firmware reconfiguration and bootloader integration verified on November 2, 2025.
