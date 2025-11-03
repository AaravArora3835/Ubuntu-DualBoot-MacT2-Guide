# USB Not Detected in Startup Manager

**Issue Date:** October 31, 2025  
**Resolved:** October 31, 2025  

---

## Problem

The Ubuntu USB installer was not appearing in the Mac Startup Manager despite being flashed with **balenaEtcher**.

---

## Cause

The USB drive was formatted using the **GUID partition scheme** but macOS caching caused it not to register immediately.  
Additionally, the Etcher process left a hidden EFI volume unmounted.

---

## Resolution Steps

1. Re-flash the ISO using Etcher (verify checksum first).  
2. Unplug and re-insert the USB.  
3. Open **Disk Utility → View → Show All Devices.**  
4. Confirm volume name shows as **Ubuntu 24.04 LTS**.  
5. Restart Mac → Hold **Option (⌥)** → Select **EFI Boot**.  

If still not visible:
```bash
sudo diskutil eraseDisk MS-DOS UBUNTU MBR /dev/diskX
sudo diskutil unmountDisk /dev/diskX
````

Then re-flash with Etcher again.

---

## Verification Screenshot

`/Screenshots/2025-10-31_USB_Format_Settings.jpg`

---

**Status:** USB drive now recognized by Startup Manager and boots correctly.

Would you like me to make one more companion file — a **Troubleshooting_Summary.md** that goes at the repo root and summarizes every problem/resolution across the entire project (for portfolio recruiters)?
