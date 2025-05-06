# 💻 Dell Inspiron 3505 Hackintosh Guide

> **DISCLAIMER:** These are the EFI files that I used to get MacOS running on my computer. For educational purposes only. Proceed at your own risk. I am NOT responsible for anything that happens to your computer.


## 🧾 System Specifications

| Component       | Details                                      |
|----------------|----------------------------------------------|
| Model           | Dell Inspiron 3505                          |
| CPU             | AMD Ryzen 5 3450U / Ryzen 3 3250U           |
| GPU             | AMD Radeon Vega 8 / Vega 3 (Integrated)     |
| RAM             | 8GB DDR4 (upgradeable)                      |
| Storage         | 256GB NVMe SSD (replaceable)               |
| Display         | 1920x1080 FHD (60Hz)                        |
| Wi-Fi/Bluetooth | Realtek RTL8821CE (incompatible, replace recommended) |
| Audio           | Realtek ALC256                             |
| Trackpad        | I2C (requires VoodooI2C)                    |

## ✅ Compatibility Summary

| Feature        | Status           | Notes                                       |
|----------------|------------------|---------------------------------------------|
| macOS Version  | ✅ Monterey, Ventura | Sonoma is **not recommended** (AMD issues) |
| Graphics        | ⚠️ Partial         | No full acceleration (AMD Vega iGPU) . Works for basic web browsing, and basic tasks.     |
| Wi-Fi           | ❌ No              | RTL8821CE not supported. Use USB dongle or replace with DW1560 |
| Audio           | ⚠️ Experimental        | Currently Expermenting with this one. Not working ATM            |
| Sleep/Wake      | ⚠️ Experimental    | May require SSDT patches                    |
| Touchpad        | ✅ Working         | Requires `VoodooI2C` and `VoodooI2CHID`     |
| XCode "Deploy to Device" | ⚠️ Partial | Apps you make will launch on your device, but will not properly deploy for testing. |


## 📁 EFI Folder

Download the latest stable EFI from the [Releases](https://github.com/yourusername/inspiron-3505-hackintosh/releases) tab.

### Contents:
- OpenCore Bootloader
- Proper SSDTs for AMD
- Kexts: Will update with a more up-to-date list at a later time
- `config.plist` (Note: for the system to boot, I had to put "USBBusFix=Yes" as a command argument)
## 🧰 Required Kexts

- Most of them are included in the uploaded  EFI folder


## 🛠 Installation Guide

1. **Install macOS**: Install MacOS to a spare SSD or MVNE Drive
2. **Replace EFI**: Mount EFI partition of your Newly installed MacOS Drive and replace with the provided `EFI` folder.
3. **BIOS Settings**:
   - Secure Boot: Disabled
   - AHCI Mode: Enabled
   - Virtualization: Enabled
   - TPM: Disabled
4. **Boot into OpenCore**
5. **Boot into macOS and complete setup**

## ⚙️ Post-Installation

- Replace the Wi-Fi card with a compatible one (e.g., Broadcom DW1560)
- Configure `AppleID` (see [Dortania's Guide](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html))

## 📝 Credits

- OpenCore Team
- Dortania Docs
- AMD OS X Community
- @IHS5452 for maintaining this repo

## 📦 License

This project is licensed under the [MIT License](LICENSE).
