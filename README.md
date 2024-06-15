# OC Dell Latitude 7370
OpenCore EFI MacOS Monterey on Dell Latitude 7370

Use at your own risk! I can not be held responsible for any damage done.

- Dell Latitude 13 7370
- CPU: Intel m7-6Y75 Dual-Core
- Graphic: Intel HD Graphics 515
- Buildin screen: 3200 x 1800 (QHD+ - Wide Quad Extended Graphics Array Plus) Display
- Memory: Onboard (4+4) = 8 GB 1866 MHz LPDDR3 RAM
- NVMExpress: 500.11 GB KINGSTON SNVS500G
- MicroSD Card reader: Vendor ID: 0x10ec, Sub-system Vendor ID: 0x1028, Device ID: 0x525a, Sub-system Device ID: 0x071b
- Camera: UVC Camera Realtek Semiconductor Corp. VendorID_3034 ProductID_22376, Product ID: 0x5768, Device ID: 0x0bda 
- Audio: Realtek ALC256 Audio (rebranded as ALC3246)
- BIOS: version 1.30.3
- OpenCore v1.0.0
- MacBook9,1 as SMBIOS
- Monterey Version 12.7.5 (21H1222)

Working:
- EC power management
- HD515 with full hardware acceleration
- USB-C charging
- Audio as AppleALC layout-id 11(0B000000)
- display brightness control
- touchpad with scrolling and two-finger-click (VoodooPS2)
- keyboard with backlight
- function keys
- microSD cardreader
- USB-C/Thunderbolt hotplug
- unlock with Apple Watch
- Messages
- FaceTime
- headphone jack (using ComboJack https://github.com/hackintosh-stuff/ComboJack)
- Wifi (2.4 and 5 Ghz)
- micro HDMI port

Not tested:
- touchscreen
- WWAN

Not working:


Recommended tools:
- MountEFI (mount EFI folder under MacOS)
- PlistEdit Pro (edit config.plist with GUI)
- DeltaWalker (compare config.plist)


BIOS setting:
- System Configuration > Thunderbolt Adapter Configuration
  - Security level - No Security
- Virtualization Support > VT for Direct I/O
  - Enabled (Now required for Thunderbolt to work in Big Sur)

BIOS tweaks:

  - disable CFG Lock: ~**setup_var 0x109 0x0**   Verify before use (extracted from BIOS 1.19.5)~\
    Use CFGLock tool to find and toggle value
  - increase DVMT:    **setup_var 0x432 0x3**   Verify before use (extracted from BIOS 1.27.3)
