<b>MX150 Only!</b>
## Introduction
According to [AptioFixPkg's README](https://github.com/acidanthera/AptioFixPkg#verifymsre2), "[c]ertain firmwares fail to properly initialize 0xE2 MSR register (MSR_BROADWELL_PKG_CST_CONFIG_CONTROL) across all the cores....

CFG Lock option is available on most APTIO V firmwares, although it may be hidden from the GUI. If VerifyMsrE2 reports that your 0xE2 register is consistently locked, you may try to unlock this option directly."

## How to Unlock

[Cyb](http://4pda.ru/forum/index.php?showuser=914121) and [FallenChromium](https://github.com/FallenChromium) created script to unlock. Please download [DVMT_and_0xE2_fix](https://github.com/daliansky/XiaoMi-Pro/tree/master/BIOS/DVMT_and_0xE2_fix) and read [README](https://github.com/daliansky/XiaoMi-Pro/tree/master/BIOS/DVMT_and_0xE2_fix/README.md) to unlock.

After that, you should delete Clover MSR 0xE2 patch.
- Open `/EFI/CLOVER/config.plist`, find and delete the following code:
```
<dict>
	<key>Comment</key>
	<string>MSR 0xE2 _xcpm_idle instant reboot(c) Pike R. Alpha</string>
	<key>Find</key>
	<data>ILniAAAADzA=</data>
	<key>Replace</key>
	<data>ILniAAAAkJA=</data>
</dict>
```

## Credits
- [Acidanthera](https://github.com/acidanthera)
  - [AptioFixPkg](https://github.com/acidanthera/AptioFixPkg)
- [Cyb](http://4pda.ru/forum/index.php?showuser=914121) and [FallenChromium](https://github.com/FallenChromium)