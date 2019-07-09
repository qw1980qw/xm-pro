## Before Install

- This is a Windows instruction
- This instruction includes a bunch of software, I am not sure whether they are safe or not
- <b>Make sure your SSD is not PM981.</b> You have to install macOS on a hard disk other than PM981.
  - `PM981` SSD's serial number starts with `MZVLB`, and `PM961` SSD's serial number starts with `MZVLW`.

- Please refer to the detailed installation tutorial [Xiaomi Mi Notebook Pro High Sierra 10.13.6](https://www.tonymacx86.com/threads/guide-xiaomi-mi-notebook-pro-high-sierra-10-13-6.242724)

- or video tutorial [Xiaomi NoteBook PRO HACKINTOSH INSTALLATION GUIDE !!!](https://www.youtube.com/watch?v=72sPmkpxCvc).


## Step 1 - Download macOS image

- There are so many macOS image resources if you google it. Choose one you like from the search results.
- I personally prefer to download from https://mirrors.dtops.cc/iso/MacOS/daliansky_macos/
<img src="https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/img/Installation_1.JPG" alt="Download Image">&nbsp;


## Step 2 - Format U-disk with the macOS image

- Download and install `etcher` from https://www.balena.io/etcher/
- Select the image you downloaded in Step 1
- Insert your U-disk and click `Flash`
<img src="https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/img/Installation_2.JPG" alt="Flash Image">&nbsp;
- Wait until finish


## Step 3 - Download XiaoMi-Pro EFI

- Download the latest release from https://github.com/daliansky/XiaoMi-Pro-Hackintosh/releases
<img src="https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/img/Installation_4.JPG" alt="Download EFI">&nbsp;
- Unzip it to the desktop


## Step 4 - Modify SSD's EFI partition

- First, you have to make sure your SSD's EFI partition is larger than 200MB. 250MB is a safe size.
  - If your EFI/ESP partition is smaller than 200MB, you can use `DiskGenius` to merge EFI and MSR partition.
  - If the total size of EFI/ESP and MSR partition is still smaller than 200MB, you need to create a new EFI partition with >200MB size.
- Download and install `DiskGenius` from https://www.diskgenius.com
- Then, backup BOOT and CLOVER folder from your EFI/ESP partition to other places
- Delete BOOT and CLOVER folders and copy these two folders from the EFI release you downloaded in Step 3
  - If there's no CLOVER folder, that's OK; Ignore the capitalization of BOOT folder, lowercase is OK
<img src="https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/img/Installation_5.jpg" alt="Copy EFI">&nbsp;


## Step 5 - Adjust boot entry

- Download `Bootice` from https://www.majorgeeks.com/mg/getmirror/bootice_64_bit,1.html
- Select your SSD in `Destination Disk`(not your U-disk!), click `Parts Manage`, select the ESP/EFI partition in the new window, and click `Assign Drive Letter`
<img src="https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/img/Installation_6.jpg" alt="Mount EFI">&nbsp;
- Remember the new letter given to the EFI/ESP partition
<img src="https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/img/Installation_7.jpg" alt="EFI Letter">&nbsp;
- Go to `UEFI` bar, click `Edit boot entries`, click `Add` and open `EFI/CLOVER/CLOVERX64.efi` in the new file browser, click `Up` to move the new entry to the top, and close the window
<img src="https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/img/Installation_8.jpg" alt="Add Clover Entry">&nbsp;
- Go back to `Physical disk` bar, click `Parts Manager`, select ESP partition, and click `Remove Drive Letter`
  - If `Remove Drive Letter` can not be clicked, reopen the software and redo this
<img src="https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/img/Installation_9.jpg" alt="Remove EFI Letter">&nbsp;


## Step 6 - Disable Secure Boot in BIOS

- Reboot the device and press F2 to get into BIOS panel
- Click `Security`, click `Set Supervisor Password` to create a password, and click `Secure Boot Mode` to disable it
  - Pleeeease remember this password deep inside your mind, there is no way to reopen BIOS panel if you forget the password!
<img src="https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/img/Installation_10.jpg" alt="Disable Secure Boot">&nbsp;
- Press F10 to save settings and exit


## Step 7 - Install macOS

- Boot your device, and use arrow key to choose `Boot macOS Install from Install macOS ~`
  - If you can not see something like the following picture, please redo [Step 5](https://github.com/daliansky/XiaoMi-Pro-Hackintosh/wiki/Installation#step-5---adjust-boot-entry)
<img src="https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/img/Installation_11.jpg" alt="Choose macOS Install">&nbsp;
- Wait until a `macOS Utilities` window shows up. Double click `Disk Utility`.
<img src="https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/img/Installation_12.jpg" alt="Open Disk Utility">&nbsp;
- If you are installing macOS on an entire separate SSD
  - Click the window button at top left and choose `Show All Devices`
<img src="https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/img/Installation_13.jpg" alt="Show All devices">&nbsp;
  - Select your target SSD and click `Erase`. Format should be `APFS`.
<img src="https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/img/Installation_14.jpg" alt="Format SSD to APFS">&nbsp;
- If you are installing macOS on a partition, select the target partition and click `Erase`. Format should be `APFS`.
  - If an error message `MediaKit reports not enough space on device for requested operation` appears, please redo [Step 4](https://github.com/daliansky/XiaoMi-Pro-Hackintosh/wiki/Installation#step-4---modify-ssds-efi-partition)
- Close this windows by clicking red button at top left, and double click `Install macOS`
<img src="https://github.com/daliansky/XiaoMi-Pro/raw/master/wiki/img/Installation_15.jpg" alt="Install macOS">&nbsp;
- Wait until finish, device will reboot several times