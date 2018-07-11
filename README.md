# Asus ZenBook Pro UX501JW for macOS High Sierra

## Overview
This repo was created to help the owners of the same laptop model with the same hardware specifications and bios version and they want to try **macOS High Sierra** (hackintosh) on their system by providing the required files & hacks for the system to run macOS High Sierra.

## Hardware Details
- **Model Name:** [ASUS ZenBook Pro UX501JW](https://www.asus.com/Laptops/ASUS-ZenBook-Pro-UX501JW/) (Bios version 211)
- **Processor:** Intel Core i7 4720HQ (2.60 GHz)
- **Chipset:** Intel HM87 Express Chipset
- **Memory:** DDR3 16GB RAM
- **Display:** 15.6" 16:9 IPS UHD (3840 x 2160)
- **Graphics:**
    - Intel HD Graphics 4600
    - NVIDIA GeForce GTX 960M 2GB
- **Storage:** SSD (PCIE x4) 512GB
- **Audio Codec:** ALC668
- **Wireless/BT:** replaced the original (Intel Wireless-AC 7260) with [AzureWave AW-CE123H](https://www.amazon.com/dp/B00HRFS1GQ/ref=psdc_13983731_t1_B00JY6X9HM)
- **Interfaces:**
    - 3 USB 3.0 ports
    - Audio combo jack
    - HDMI
    - SD card reader
    - Mini Display Port (Thunderbolt in some models)
- **Camera:** HD web camera

## Results
The following resulted from my own work (with the help of other people in this community) on installing High Sierra on this laptop model, but it does not mean it is the final results, so if you discovered a better way to fix some of the issues be my guest and create an issue.

### Working
- Full QE/CI for Intel HD4600 @1920x1080 (NVIDIA GPU will be disabled)
- Audio (internal speakers with key control / 3.5mm jack / Internal Microphone)
- WIFI & BT (handoff, universal clipboard, cellular calls, SMS and MMS)
- Keyboard (with backlight control)
- Trackpad (simple gestures)
- Laptop Display / Brightness (with key control)
- HDMI video output
- USB ports
- Camera
- SSD (GPT with APFS)
- CPU power management
- Sleep
- Battery info

### Working with bugs
- Full QE/CI for Intel HD4600 @3840x2160 with screen flickering badly.
- Audio 3.5mm jack: if you experience any noise when using a headset just open System Preferences > Sound > Input, and switch from the Internal Microphone (Built-In) to the Line In (Audio line-in port) and the noise will disappear immediately, sometimes you need to keep the System Preferences window open on the Sound > Input panel in order to keep the noise off.

### Not working
- Audio (HDMI)
- Instant Hotspot (shows as supported but never connects)

### Not tested
- Thunderbolt / mini display port
- SD card reader (experimental kext loaded but not tested)

## Bios Settings
Detailed bios settings for the working machine:

### Advanced menu
- Internal Pointing Device [Enabled]
- Wake On Lid Open [Enabled]
- Power Off Energy Saving [Enabled]
- Intel Virtualization Technology [Enabled]
- Intel AES-NI [Enabled]
- VT-d [Disabled]
- Trusted Computing:
    - Security Device Support [Disabled]
- SATA Configuration
    - SATA Mode Selection [AHCI]
- Graphics Configuration
    - DVMT Pre-Allocated [128M]
- USB Configuration
    - Legacy USB Support [Enabled]
    - XHCI Pre-Boot Mode [Smart Auto]
- Intel (R) Thunderbolt
    - Security Level [Unique ID]
- Network Stack
    - Network Stack [Disabled]

### Boot menu
- Launch CSM [Enabled], it does not matter if enabled or disabled except for the CLOVER boot menu resolutions, to get higher resolutions set this option to disabled without installing `CsmVideoDxe-64.efi` driver.

### Security menu
- I/O Interface Security
    - Wireless Network Interface [UnLock]
    - HD AUDIO Interface [UnLock]
    - Card Reader [UnLock]
    - USB Interface Security
        - USB Interface [UnLock]
        - External Ports [UnLock]
        - BlueTooth [UnLock]
        - CMOS Camera [UnLock]
- Secure Boot Control [Disabled]

**Enjoy**