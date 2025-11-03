# Secure Boot Configuration Error

**Issue Date:** October 30, 2025  
**Resolved:** October 30, 2025  

---

## Problem

When booting from the Ubuntu USB, macOS displayed:
> “Security settings do not allow this Mac to use an external startup disk.”

The T2 Security Chip prevented booting unsigned OS media.

---

## Cause

The default T2 Secure Boot setting “Full Security” validates Apple-signed operating systems only.  
This blocked the unsigned Ubuntu bootloader from initializing.

---

## Resolution Steps

1. Boot into **macOS Recovery** (hold ⌘ + R).  
2. Open **Startup Security Utility.**  
3. Authenticate with admin credentials.  
4. Change:
   - **Secure Boot:** *No Security*  
   - **External Boot:** *Allow booting from external media*  
5. Restart the Mac and reconnect the Ubuntu USB.  
6. Hold **Option (⌥)** during boot → select **EFI Boot (orange USB icon).**

---

## Verification Evidence

- `/Screenshots/2025-10-30_SecureBoot_Settings.jpg`  
- `/Screenshots/2025-10-31_EFI_Boot_Menu.jpg`  

---

**Status:** Ubuntu installer now boots successfully from USB.  
**Next Step:** Proceed with partition setup and checksum verification.
