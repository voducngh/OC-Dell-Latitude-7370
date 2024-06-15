# OC Dell Latitude 7370
OpenCore EFI MacOS Monterey on Dell Latitude 7370

Use at your own risk! I can not be held responsible for any damage done.

- Dell Latitude 13 7370
- Intel m7-6Y75 Dual-Core
- Intel HD515
- 8 GB 1866 MHz LPDDR3 RAM
- WD NVME 500GB
- Broadcom BCM943602CS (using M.2 Key A+E adapter) with third antenna
- Dell 5809e Gobi (Sierra Wireless EM7305) 4G LTE WWAN
- 1920x1080@60Hz HD Display
- Realtek ALC256 Audio (rebranded as ALC3246)
- BIOS version 1.30.3
- OpenCore v1.0.0
- MacBook9,1 as SMBIOS


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
- SideCar (not tested)
- headphone jack (using ComboJack https://github.com/hackintosh-stuff/ComboJack)
- Wifi (2.4 and 5 Ghz)
- WWAN (not tested)
- micro HDMI port

Not working:
- nothing

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
