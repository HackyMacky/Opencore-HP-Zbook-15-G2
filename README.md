# Opencore HP Zbook 15 G2
This is an Opencore EFI repository of my HP Zbook 15 G2. **DISCLAIMER:** I will not be held responsible for any damage, permanent loss of data or any sorts of consequences that may arise by using my configuration files on your devices. Please use at your own risk.

## Current Release
- Opencore 0.7.9
- Monterey 12.3
- All latest kexts as of March 15, 2022

## Notebook Specifications

| Specification  | Model |  Remark  |
| ------------- | ------------- | ------------- |
| Chipset  | Mobile Intel QM87 | M70 v01.26 (3/3/2020)  |
| CPU  | Intel i7-4810MQ  |
| iGPU  | Intel HD4600  | Intel (R) vBios 5.5.1028  |
| dGPU  | Nvidia Quadro K1100M (Disabled)  |
| Storage  | Samsung Evo 870 SATA 2.5 256GB  |
| RAM  | 16GB (4x4GB) Micron PC3L |
| Ethernet  | Intel I217-LM  |
| Wi-Fi  | Intel Wireless AC-7260  |
| Bluetooth  | Intel Bluetooth   |
| Audio  | Realtek ALC3228 (ALC280)   |
| Touchpad  | Synaptic SMBus Touchpad   |
| Inputs  | HP PS2 KB & Mouse  |

## What's working
- Mostly everything
- Wi-Fi & toggle button, Bluetooth, Ethernet
- Battery readouts
- Screen brightness adjustment
- Keyboard backlight
- Speakers, headphone jack, microphone, volume adjustments keys, sound toggle button
- USB ports
- HP Camera
- Sleep/wake

## What's not working
- Displayport, Thunderbolt port 
- SD Card reader
- Nvidia K1100M

## Not tested
- VGA port
- AppleID and iServices

## Some quirks/issues
- While loading the installer (DEBUG version), it may stop at EXITBS:START giving an impression of a kernel panic. Give it at least 10 minutes at most and it should continue.
- The DGPU is only disabled but not completely powered off. While this reduces power consumption, do take note that it is still sipping power slowly in the backend. The SSDT to power off the DGPU is included in the config.plist but not enabled. Enabling this SSDT will power off the DGPU but somehow loses fan control hence resulting in the laptop fan running at max rpm. (hoping someone can help fix this)
- The touchpad might experience lags for 30 seconds upon boot but works well after.
- Touchpad might be unresponsive after waking from sleep

## Bios Settings
- Disable **Fast Boot**
- Enable **USB device boot**
- Set Boot Mode to **UEFI Hybrid (With CSM)**
- Device Configurations
  - Enable **Fn Key switch**
  - Enable **USB 3.0 (XHCI)**
  - Video memory size **64 MB**
  - SATA Device Mode: **AHCI**
  - Enable **Virtualization Technology (VTx)**
  - Disable **Virtualization Technology for Directed I/O (VTd)**
  - Disable **Trusted Execution Technology**
  - Enable **Intel(R) HT Technology**
  - Enable **Hybrid Graphics**
- Built-in Device Options
  - Enable **Wireless Button state**
  - Enable **Embedded Bluetooth Device**
  - Enable **Embedded LAN Controller**
  - Disable **Wake on LAN**
- Port Options
  - Disable **Serial & Parallel port**

## Credits
- All credits & rights goes to the maintainers, contributors and developers of the Opencore project and respective kernel extensions.
- Apple Inc.
