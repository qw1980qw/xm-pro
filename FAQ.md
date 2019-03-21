## Installation
<b>Q: KP occurs on PM981</b>

A: Currently there's [no solution for PM981 on macOS 10.13.3+](https://www.tonymacx86.com/threads/how-to-fix-pm981-in-10-13-3-17d47.245063). You could install macOS on another hard disk.
- `PM981` SSD's serial number starts with `MZVLB`, and `PM961` SSD's serial number starts with `MZVLW`.

## Audio
<b>Q: Headphones is not working after sleep</b>

A: If headphones are not working, please use [ALCPlugFix](https://github.com/daliansky/XiaoMi-Pro/tree/master/ALCPlugFix/README.md). You may need to replug headphone after every boot. This issue seems solved in [v1.3.0 Release](https://github.com/daliansky/XiaoMi-Pro/releases/tag/v1.3.0).

## Bluetooth
<b>Q: Bluetooth is not working after long sleep or hard restart</b>

A: Native Intel Bluetooth is [not working well](https://github.com/daliansky/XiaoMi-Pro/issues/50) in macOS. You can disable it, use a USB BT dongle, or solder D+ and D- wires to the WLAN_LTE slot. See [[Work Around with Bluetooth]].

## Boot
<b>Q: Device is locked by `Find My Mac`</b>

A: Press `Fn+F11` when you are in Clover boot page. Then Clover will refresh `nvram.plist`, and lock message should be removed.

<b>Q: Fail to boot in Windows/Linux by using Clover, but able to boot by pressing F12 and select OS</b>

A: Many people met this problem by using the new version of `AptioMemoryFix.efi`. A workaround is to replace `/CLOVER/drivers64UEFI/AptioMemoryFix-64.efi` with an [older version](https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/AptioMemoryFix-64.efi).

<b>Q: `FileVault` encrypted the macOS partition and the partition does not show up</b>

A: It is not recommended to enable `FileVault`. You can press Fn + F3 in the Clover boot page and choose the icon with `FileVault`. Then you can boot in the system and disable `FileVault`.

## HDMI
<b>Q: Internal screen turns to black when plug in an external monitor</b>

A: To be honest, I have no idea why this happens, maybe related to framebuffer pipe. A workaround is to close the lids for about five seconds and reopen it.

## Trackpad
<b>Q: Trackpad is not working</b>

A: You need to rebuild the kext cache after every system update. Use `Kext Utility.app` or type `sudo kextcache -i /` in `Terminal.app`. Then restart. If this still doesn't work, try to press F9 or warm reboot from Windows.

<b>Q: Lag when type</b>

A: The latest keyboard driver can temporally disable the trackpad during typing. If you are not happy with the lag, please replace `/CLOVER/kexts/Other/VoodooPS2Controller.kext` with the [older version of VoodooPS2Controller.kext](https://github.com/daliansky/XiaoMi-Pro/tree/master/wiki/VoodooPS2Controller.kext).

## Keyboard
<b>Q: Caps Lock is not working</b>

  - Add `Pinyin - Simplified` in `SysPref- Keyboard - Input Sources`
  - Uncheck `Use the Caps Lock key to switch to and from ABC`
  - Delete `Pinyin - Simplified` and done

## Wi-Fi
<b>Q: Wi-Fi is not working</b>

A: Intel Wireless Card could never work on macOS. Please use a USB WiFi dongle or insert a supported wireless card into M.2 slot. More information can be viewed in [Xiaomi Mi Notebook Pro High Sierra 10.13.6](https://www.tonymacx86.com/threads/guide-xiaomi-mi-notebook-pro-high-sierra-10-13-6.242724).

<b>Q: Location Service/AirDrop/Handoff is not working</b>

A: Location Service/AirDrop/Handoff needs a supported internal wireless card to work(A few USB dongles can use location service, I don't know why). AirDrop and Handoff also need stable bluetooth connection, see [[Work Around with Bluetooth]].