## Installation
### Q: KP occurs on PM981
A: Currently there's [no solution for PM981 on macOS 10.13.3+](https://www.tonymacx86.com/threads/how-to-fix-pm981-in-10-13-3-17d47.245063). You could install macOS on another hard disk.
- `PM981` SSD's serial number starts with `MZVLB`, and `PM961` SSD's serial number starts with `MZVLW`.

## Audio
### Q: Headphones not working after sleep
A: If headphones are not working, please use [ALCPlugFix](https://github.com/daliansky/XiaoMi-Pro/tree/master/ALCPlugFix/README.md). You may need to replug headphone after every boot. This issue seems solved in [v1.3.0 Release](https://github.com/daliansky/XiaoMi-Pro/releases/tag/v1.3.0).

## Bluetooth
### Q: Bluetooth not working after long sleep or hard restart
A: Native Intel Bluetooth is [not working well](https://github.com/daliansky/XiaoMi-Pro/issues/50) in macOS. You can disable it, use a USB BT dongle, or solder D+ and D- wires to the WLAN_LTE slot.

## Boot
### Q: Device is locked by `Find My Mac`
A: I believe there are many ways to solve this problem. I give a most understandable one here (at least for me). The solution is to refresh your BIOS in order to clean `nvram.plist`. Please read `How to update BIOS` in [BIOS folder](https://github.com/daliansky/XiaoMi-Pro/master/BIOS/README.md).

### Q: Fail to boot in Windows/Linux by using Clover, but able to boot by pressing F12 and select OS
A: Many people met this problem by using the new version of `AptioMemoryFix.efi`. A workaround is to delete `AptioMemoryFix-64.efi` in `/CLOVER/drivers64UEFI/` and replace it with the old version provided in [#93](https://github.com/daliansky/XiaoMi-Pro/issues/93).

### Q: `FileVault` encrypted the macOS partition and the partition does not show up
A: It is not recommended to enable `FileVault`. You can press Fn + F3 in the Clover boot page and choose the icon with `FileVault`. Then you can boot in the system and disable `FileVault`.

## HDMI
### Q: Internal screen turns to black when plug in an external monitor
A: To be honest, I have no idea why this happens, maybe related to framebuffer pipe. A workaround is to close the lids for about five seconds and reopen it.

## Trackpad
### Q: Trackpad not working
A: You need to rebuild the kext cache after every system update. Use `Kext Utility.app` or type `sudo kextcache -i /` in `Terminal.app`. Then restart. If this still doesn't work, try to press F9 or warm reboot from Windows.

### Q: Lag when type
A: The latest keyboard driver can temporily disable the touchpad during typing. If you are not happy with the lag, a workaround is provided in [#19](https://github.com/stevezhengshiqi/XiaoMi-Pro/issues/19).

## Keyboard
### Q: Caps Lock not working
  - Add `Pinyin - Simplified` in `SysPref- Keyboard - Input Sources`
  - Uncheck `Use the Caps Lock key to switch to and from ABC`
  - Delete `Pinyin - Simplified` and done

## Wi-Fi
### Q: Wi-Fi not working
A: Intel Wireless Card could never work on macOS. Please use a USB WiFi dongle or insert a supported wireless card into M.2 slot. More information can be viewed in [Xiaomi Mi Notebook Pro High Sierra 10.13.6](https://www.tonymacx86.com/threads/guide-xiaomi-mi-notebook-pro-high-sierra-10-13-6.242724).