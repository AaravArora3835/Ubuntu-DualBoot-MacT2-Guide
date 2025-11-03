# T2 Keyboard and Trackpad Fix

**Issue Date:** November 2, 2025  
**Resolved:** November 2, 2025  

---

## Problem

After successfully booting Ubuntu 24.04, the internal keyboard and trackpad were unresponsive.  
Only external USB input devices functioned.

---

## Cause

T2 Mac models require the **apple-bce** (Bridge Controller Enabler) kernel module, which is not included in the stock Ubuntu kernel.

---

## Resolution Steps

1. Connect external keyboard/mouse.  
2. Connect to internet using USB tethering or Ethernet.  
3. Open Terminal and run:
   ```bash
   sudo apt update
   sudo apt install dkms git build-essential linux-headers-$(uname -r) -y
   git clone https://github.com/t2linux/apple-bce-dkms.git
   cd apple-bce-dkms
   sudo ./install.sh
   sudo reboot

4. After reboot, verify:

   ```bash
   lsmod | grep bce
   ```

   → Output shows `apple_bce` module loaded.

---

## Verification Screenshot

`/Screenshots/2025-11-02_T2_Keyboard_Trackpad_Fix.jpg`

---

**Status:** Internal keyboard and trackpad working under Ubuntu 24.04 LTS.
**Next Step:** Test multitouch and suspend/resume behavior.
