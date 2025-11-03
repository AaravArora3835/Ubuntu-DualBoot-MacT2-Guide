# Complete Guide — Ubuntu 24.04 LTS Dual-Boot on MacBook Pro (2019 T2 Chip)

**Author:** Aarav Arora  
**Updated:** November 2, 2025  
**Time Required:** ~8 Hours (1 day)  

---

## 1. Preparation

### Required Tools
- Ubuntu 24.04 LTS ISO  
- Balena Etcher 2.1.4  
- rEFInd Boot Manager 0.14.0.2  
- 16 GB USB drive  
- macOS Ventura or Monterey host  
- External keyboard/mouse (optional)  
- Stable Wi-Fi or Ethernet connection  

### Pre-Install Steps
1. Download Ubuntu ISO from [ubuntu.com](https://ubuntu.com/download/desktop).  
2. Verify checksum:  
   ```bash
   shasum -a 256 ubuntu-24.04.3-desktop-amd64.iso

Compare with official SHA-256 on Ubuntu site.
3. Flash to USB with Etcher.
4. Backup macOS via Time Machine.

---

## 2. Firmware Configuration

1. Reboot into macOS Recovery (⌘ + R).
2. Open **Startup Security Utility**.
3. Set **Secure Boot:** No Security.
4. Set **External Boot:** Allow booting from external media.
5. Disable SIP:

   ```bash
   csrutil disable
   reboot
   ```
6. Install rEFInd:

   ```bash
   ./refind-install
   ```
7. Verify EFI menu on next boot.

---

## 3. Installation Phase

1. Boot Mac → hold **Option (⌥)** → select **EFI Boot**.
2. Choose “Try Ubuntu” to load live environment.
3. Test keyboard/mouse and display.
4. Start **Install Ubuntu 24.04 LTS**.
5. Select “Install alongside macOS.”
6. Allocate ~70 GB to Ubuntu (ext4).
7. Check “Download updates while installing” + “Install third-party software.”
8. Create user account and strong password.
9. Wait ~20 minutes.
10. Remove USB → Restart.

---

## 4. Post-Install Verification

1. Confirm rEFInd shows both macOS and Ubuntu.
2. Boot into Ubuntu → open Terminal.
3. Run system updates:

   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
4. Fix Broadcom Wi-Fi (if needed):

   ```bash
   sudo apt install firmware-b43-installer -y
   ```
5. Install Apple BCE drivers for keyboard/trackpad:

   ```bash
   sudo apt install dkms git build-essential -y
   git clone https://github.com/t2linux/apple-bce-dkms.git
   cd apple-bce-dkms && sudo ./install.sh
   sudo reboot
   ```
6. Verify input devices and Wi-Fi functionality.

---

## 5. Boot Order and Maintenance

1. If Ubuntu overwrites boot order:

   ```bash
   sudo efibootmgr -o 0001,0000,0002
   ```
2. Verify EFI entries and rEFInd priority.
3. Re-enable SIP after stability testing:

   ```bash
   csrutil enable
   ```
4. Optional: Set Secure Boot to Medium Security.
5. Keep `apple-bce` and `rEFInd` updated for kernel changes.

---

## 6. Verification Checklist

✅ Ubuntu and macOS boot normally
✅ rEFInd appears by default
✅ Wi-Fi and trackpad working
✅ No EFI or GRUB errors
✅ All resources documented and timestamped

---

## 7. Educational Value

This guide serves as a teaching-quality reference for cybersecurity students learning:

* Firmware security principles (Secure Boot, SIP)
* Dual-boot and EFI architecture
* Linux driver troubleshooting and package management
* Evidence-based documentation in system administration

---

**Outcome:**
A fully auditable Ubuntu–macOS dual-boot lab environment, optimized for hands-on cybersecurity training and real-world system management skills.
