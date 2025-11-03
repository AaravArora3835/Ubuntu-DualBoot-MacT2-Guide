# SIP Issue and Resolution

**Issue Date:** October 31, 2025  
**Resolved:** October 31, 2025  
**System:** MacBook Pro (2019, T2 Security Chip)  

---

## Problem

The **System Integrity Protection (SIP)** feature in macOS blocked the **rEFInd boot manager** from writing to the EFI partition.  
Attempting to run `./refind-install` resulted in:  
```

Error: Cannot write to EFI directory. Operation not permitted.

````

---

## Cause

SIP restricts write access to system-protected directories, including `/System` and `/EFI`.  
Without disabling SIP, the rEFInd installer cannot place EFI files in the required partition.

---

## Resolution Steps

1. Reboot into **macOS Recovery** (hold ⌘ + R).  
2. Open **Utilities → Terminal.**  
3. Run:
   ```bash
   csrutil disable
   reboot
``

4. Verify:

   ```bash
   csrutil status
   ```

   → “System Integrity Protection status: disabled.”

5. Re-run the rEFInd installer:

   ```bash
   ./refind-install
   ```

   Confirm success message and reboot.

---

## Post-Installation Note

SIP remains temporarily disabled to support EFI reconfiguration.
It will be re-enabled once keyboard/trackpad drivers are stable and no further EFI edits are needed.
To re-enable:

```bash
csrutil enable
```

---

**Verification Screenshot:**
`/Screenshots/2025-10-31_SIP_Status_Disabled.jpg`

````
