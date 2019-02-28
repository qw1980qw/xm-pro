## Introduction
As we know, the Bluetooth would be invalid after long sleep or hard restart. Because there're no driver for Intel Bluetooth in macOS, the Bluetooth hardware is not able to receive firmware from Hack. As a result, you need to warm restart from Windows to get Bluetooth run. There're three ways to get better BT experience:

- ### Insert a USB Bluetooth
  - Buy and insert a supported BT dongle from [OS-X-BrcmPatchRAM's README](https://github.com/RehabMan/OS-X-BrcmPatchRAM/master/README.md)
  - Replace `USBPorts` with the one in [#24](https://github.com/daliansky/XiaoMi-Pro/issues/24)
  - Add `BrcmPatchRAM2.kext` and `BrcmFirmwareRepo.kext`(/L/E) or `BrcmFirmwareData.kext`(CLOVER/kexts/Other)
  - Rebuild kextcache and restart 

- ### Solder D+ and D- wires to the WLAN_LTE slot
  - Buy and insert a supported internal wireless card(e.g. BCM943602CS) in M.2 slot
  - Carefully solder D+ and D- wires to the WLAN_LTE slot as [#7](https://github.com/stevezhengshiqi/XiaoMi-Pro/issues/7)
  - Go to Windows, run `Device Manager` to check whether the soldering is success or not
  - If success, replace `USBPorts` with the one in [#7](https://github.com/stevezhengshiqi/XiaoMi-Pro/issues/7)

- ### (Not tested) Use VM to upload Bluetooth firmware
  - Read [black.dragon74](https://osxlatitude.com/profile/86692-blackdragon74)'s [instruction](https://osxlatitude.com/forums/topic/10127-updated-nov-2017-fix-btfirmwareuploader-in-macos-high-sierra)