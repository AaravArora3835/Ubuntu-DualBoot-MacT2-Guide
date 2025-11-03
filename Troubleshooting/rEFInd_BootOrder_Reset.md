# rEFInd Boot Order Reset After Ubuntu Installation

**Issue Date:** November 2, 2025  
**Resolved:** November 2, 2025  

---

## Problem

After completing the Ubuntu installation, the system booted directly into Ubuntu GRUB, bypassing rEFInd.

---

## Cause

Ubuntu’s installer automatically places GRUB at the top of the EFI boot order, overriding the rEFInd entry created earlier.

---

## Resolution Steps

1. Boot into Ubuntu.  
2. Check current EFI order:
   ```bash
   sudo efibootmgr

3. Identify entry numbers:

   * rEFInd → e.g. `Boot0001`
   * Ubuntu → e.g. `Boot0000`
   * macOS → e.g. `Boot0002`
4. Re-order entries:

   ```bash
   sudo efibootmgr -o 0001,0000,0002
   ```
5. Reboot — rEFInd menu should now appear by default.

---

## Verification Screenshot

`/Screenshots/2025-11-02_rEFInd_Both_OS.jpg`

---

**Status:** Boot manager priority restored.
**Next Step:** Confirm persistent boot order after system update.
