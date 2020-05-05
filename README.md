# ASUS TP300LD EFI System Partition

This repository contains files and folder inside the EFI System Partition (ESP) on my ASUS TP300LD notebook. This ESP contains some bootloaders and UEFI tools to boot to the operating systems I used, which are mainly macOS (hackintosh) and Windows.

## List of Contents
* [ASUS TP300LD EFI System Partition](#asus-tp300ld-efi-system-partition)
  * [List of Contents](#list-of-contents)
  * [Specification of ASUS TP300LD](#specification-of-asus-tp300ld)
  * [Bootloader Information](#bootloader-information)
    * [UEFI Drivers Used](#uefi-drivers-used)
  * [[OS] macOS (Hackintosh) Information](#os-macos-hackintosh-information)
    * [macOS Version](#macos-version)
    * [Works on macOS](#works-on-macos)
    * [Not Works / Problems on macOS](#not-works--problems-on-macos)
    * [macOS Kernel Extensions (Kext) Used (by load order)](#macos-kernel-extensions-kext-used-by-load-order)
  * [[OS] Windows Information](#os-windows-information)
    * [Windows Version](#windows-version)
    * [Works on Windows](#works-on-windows)
  * [[OS] Ubuntu Information](#os-ubuntu-information)
    * [Ubuntu Version](#ubuntu-version)
    * [Works on Ubuntu](#works-on-ubuntu)
  * [Authors](#authors)
  * [License](#license)

## Specification of ASUS TP300LD
- **Processor**: Intel® Core™ i7-4510U
- **Chipset**: Intel® 8 Series Chipset
- **Integrated Graphic**: Intel® HD Graphics 4400 
- **Discrette Graphic**: NVIDIA® GeForce® 820M with 2GB DDR3 VRAM
- **Memory**: 1 x Micron 4GB DDR3L 1600Mhz SDRAM
- **Storage**: 1 x Adata SSD 250GB
- **Audio**: Realtek ALC233
- **Wi-Fi**: Broadcom BCM94352HMB (Bluetooth Combo)
- **Touchpad**: ELAN ETD PS/2 Interface
- **Touchscreen**: Atmel Touchscreen USB Interface
- **Screen Size**: 13.1 inches
- **Native Display Resolution**: 1366x768 
- **Ports**: 
  - 2 x USB 3.0
  - 1 x USB 2.0
  - 1 x HDMI out
  - 1 x power jack
  - 1 x combo audio jack
- **Battery**: 3 cells polymer battery, 50 watthours
- **BIOS Version**: TP300LD.300 (25 June 2019)

## Bootloader Information
This ESP contains these bootloaders.

- **[PRIMARY BOOTLOADER]** [OpenCore](https://github.com/acidanthera/OpenCorePkg) 0.5.8
- [Clover](https://github.com/CloverHackyColor/CloverBootloader) v5.0 r5108
- Windows Boot Manager

The boot mode used is **UEFI** with **CSM disabled** on **GUID Partition Table (GPT)** storage scheme.

### UEFI Drivers Used 
These are the UEFI drivers used by OpenCore and Clover.

#### OpenCore
- HfsPlus
- OpenRuntime
- OpenCanopy

#### Clover
- HfsPlus
- ApfsDriverLoader
- OcQuirks
- FwRuntimeServices
- VirtualSmc
 
## [OS] macOS (Hackintosh) Information
This ESP contains bootloader configured to run the following macOS, including what are works and what are not works.

### macOS Version
- **OS Version**: macOS Catalina 10.15.4 (19E287)
- **Installer**: Retail from the App Store, created using createinstallmedia

### Works on macOS
- [x] QE/CI Enabled Graphics of Intel® HD Graphics 4400 
- [x] Wi-Fi
- [x] Bluetooth
- [x] Touchpad
- [x] Touchscreen (using [Touch-Base UPDD](https://touch-base.com/drivers))
- [x] Camera
- [x] Audio output (internal speaker + external jack)
- [x] Audio input (external jack)
- [x] Volume *fn* and side keys (for volume up, volume down, and mute)
- [x] Screen brightness *fn* keys (for brightness up and down)
- [x] All USB Ports (2.0 & 3.0)
- [x] Battery status indicator
- [x] HDMI out (video + audio)
- [x] Sleep, Shutdown, and Restart
- [x] Sleep and Wake with Lid

### Not Works / Problems on macOS
- [ ] Discrette Graphic of NVIDIA® GeForce® 820M (NVIDIA Optimus switchable graphic is not supported by hackintosh)
- [ ] Audio input (internal mic)
- [ ] Audio output (external jack) distorted after sleep; must select an audio input in the Sound Preference Pane and keep the Sound Preference Pane open (otherwise, it will be distorted back when the Sound Preference Pane window is closed)

### macOS Kernel Extensions (Kext) Used (by load order)
Both OpenCore and Clover configured to have the same kernel extensions. Yet, the OpenCore bootloader loads the kexts with a configured order.

1. Lilu
2. VirtualSMC
3. AsusSMC
4. SMCProcessor
5. SMCLightSensor
6. SMCSuperIO
7. SMCBatteryManager
8. NoTouchID
9. ApplePS2SmartTouchPad
10. ApplePS2Keyboard
11. ApplePS2Controller
12. WhateverGreen
13. AppleALC
14. USBPorts
15. AirportBrcmFixup
16. BrcmFirmwareData
17. BrcmBluetoothInjector
18. BrcmPatchRAM3
19. HibernationFixup

## [OS] Windows Information
This ESP contains bootloader configured to run the following Windows.

### Windows Version
- **OS Version**: Windows 10 Home Single-Language 1910
- **Installer**: Directly downloaded from Windows website 

### Works on Windows
All components are obviously working okay.

## [OS] Ubuntu Information
This ESP contains bootloader configured to run the following Ubuntu.

### Ubuntu Version
- **OS Version**: Ubuntu 20.04 LTS (Focal Fossa)
- **Installer**: Directly downloaded from Ubuntu website 

### Works on Ubuntu
All components are obviously working okay.

## Authors
- **Danang Galuh Tegar Prasetyo** - [danang-id](https://github.com/danang-id)

## License
This project is licensed under the Apache 2.0 License - see the [LICENSE](LICENSE) file for details.
