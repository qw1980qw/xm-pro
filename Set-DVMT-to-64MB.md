## Introduction
According to [[Guide] Alternative to the minStolenSize patch with 32mb DVMT-prealloc](https://www.tonymacx86.com/threads/guide-alternative-to-the-minstolensize-patch-with-32mb-dvmt-prealloc.221506), "[a] common problem with Broadwell/Skylake/KabyLake is relatively small DVMT-prealloc setting by PC OEMs. The Apple framebuffer kexts generally assume 64mb or larger, and most PC OEMs use only 32mb." In this way, we patch the framebuffer to fit within the 32mb DVMT-prealloc in the build.

However, I found that 32MB DVMT seems don't support 4K display even with `-cdfon` boot argument in the XiaoMi-Pro case. Set DVMT to 64MB and remove framebuffer patch could let our hacks natively support 4K.

## How to Install
[Cyb](http://4pda.ru/forum/index.php?showuser=914121) and [FallenChromium](https://github.com/FallenChromium) created script to set DVMT. Please download [DVMT_and_0xE2_fix](https://github.com/daliansky/XiaoMi-Pro/master/BIOS/DVMT_and_0xE2_fix) and read [README](https://github.com/daliansky/XiaoMi-Pro/master/BIOS/DVMT_and_0xE2_fix/README.md) to set DVMT to 64MB.

<b>ATTENTION: HDMI ports use HDMI 1.4 protocol, which means only support 4K 30Hz HDMI.</b>

After that, you need to remove framebuffer patch:
- Open `/EFI/CLOVER/config.plist`, delete the following code and restart:
```
    <key>framebuffer-fbmem</key>
    <data>AACQAA==</data>
    <key>framebuffer-stolenmem</key>
    <data>AAAwAQ==</data>
```
- Reopen the lid after connecting the external monitor.

## Credits
- [Rehabman](https://www.tonymacx86.com/members/rehabman.429483)
  - [[Guide] Alternative to the minStolenSize patch with 32mb DVMT-prealloc](https://www.tonymacx86.com/threads/guide-alternative-to-the-minstolensize-patch-with-32mb-dvmt-prealloc.221506)
- [Cyb](http://4pda.ru/forum/index.php?showuser=914121) and [FallenChromium](https://github.com/FallenChromium)