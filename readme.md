⚠️ **WARNING: You must add your own serial number in `EFI/OC/config.plist`.** Related fields are:
 - PlatformInfo 
   - Generic 
     - MLB 
     - SystemSerialNumber
     - SystemUUID

You can generate some random numbers by [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS). See [official guide](https://dortania.github.io/OpenCore-Install-Guide/config.plist/comet-lake.html#platforminfo) for details.


⚠️After install/upgrade(everytime) system.you should use [OpenCore-Legacy-Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher/releases) to enable WiFi.
Method:
OpenCore-Legacy-Patcher - Post-install Root Patch - Start Root Patching

## Hardware

- **Motherboard:** 
  - MSI B760M MORTAR MAX WIFI
    - Ethernet: Realtek RTL8125B PCI Express 2.5 Gigabit Ethernet
    - Audio Codec: Realtek ALC897 Codec
- **Wireless & Bluetooth**: FENVi T919 (BCM94360CD) 1300Mbps|867Mbps
- **RAM:** 
  - A-DATA (AX5U6000C3616G-B) DDR5 6000 16GB*2
- **CPU:** Intel Core i9 13900K (iGPU not working)
- **dGPU:** Yeston AMD RX 6600 8G
- **Storage:** 
  1. hiksemitech C4000 2000GB - nvme
  1. hiksemitech C2000 1000GB - nvme
  1. WD HC550 (WUH721816ALE6L4) 16T sata 3.5" HDD
  1. WD HC550 (WUH721816ALE6L4) 16T sata 3.5" HDD

 - **Monitor**:
   1. RICRSS H28F31Z 4K 60Hz - HDMI   
   1. RICRSS H28F31Z 4K 60Hz - DP


## System

- **OS:** macOS Ventura 15.3.2
- **Bootloader:** OpenCore 1.0.4

## BIOS Settings

MSI B760M MORTAR MAX WIFI ver **7E01vHD** build 2025-03-20 [BIOS](https://www.msi.com/Motherboard/MAG-B760M-MORTAR-MAX-WIFI/support)

- SETTINGS 
  - Advanced:
    - PCIe/PCI Sub-system Settings 
      - Re-size BAR Support: **Disabled**
    - Integrated Peripherals 
      - External SATA Controller Mode: **AHCI Mode**
    - Integrated Graphics Configuration
      - Initiate Graphic Adapter: **PEG**
      - IGD Multi-Monitor: **Enabled**
    - Intel (R) Thunderbolt
      - PCIE Tunneling over USB4: **Disabled**
      - Discrete Thunderbolt(TM) Support: **Disabled**
    - Power Management Setup
      - ErP Ready: **Enabled**
    - Wake Up Event Setup
      - Wake Up Event By:**OS**
    - USB Configuration 
      - XHCI Hand-off: **Enabled**
    - BIOS CSM/UEFI Mode: **UEFI**
  - Boot:
    - MSI Fast Boot: **Disabled**
    - Fast Boot: **Disabled**

  - Security 
    - Secure Boot 
      - Secure Boot: **Disabled**

- OC 
  - CPU Features:
    - Intel Virtualization Tech (VT-x): **Enabled**
    - Intel VT-D Tech: **Disabled**
    - CFG Lock: **Disabled**



## What's working

- ✅ OpenCore GUI Picker
- ✅ dGPU
- ✅ Restart / Shutdown
- ✅ Sleep / Wake
- ✅ USB
- ✅ macOS & Windows 11
- ✅ WiFi 
- ⚠️ Bluetooth
  -  After wake ,bluetooth will be unnormal. 
  -  Turn off and then turn on Bluetooth switch will let bluetooth work again.
  -  You can use sleepwatcher to auto switch Bluetooth
```zsh
      brew install sleepwatcher blueutil
      brew services start sleepwatcher
      echo '/usr/local/bin/blueutil -p 0' > ~/.sleep
      echo '/usr/local/bin/blueutil -p 1' > ~/.wakeup
      chmod +x ~/.sleep ~/.wakeup
```
