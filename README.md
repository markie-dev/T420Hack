# T420 Hackintosh Mojave

 - from [this guide](https://www.insanelymac.com/forum/topic/285678-lenovo-thinkpad-t420-with-uefi-only/?page=20&tab=comments#comment-1952283)
 - efi from [this repo](https://github.com/tluck/Lenovo-T420-Clover)

 ### **BIOS SETTINGS**

 - Recommended is BIOS v1.46 (and stay on 1.46 if you want use a modded bios - but there are v1.48 and v1.49 mods now)
 - Recommended: reset to defaults. Most defaults settings will work - but check these settings:
 - Set Config / Serial ATA (SATA) / SATA = AHCI
 - Set Security / Memory Protection / Execution Prevention = Enabled
 - Disable Discrete Nvidia/Optimus (use integrated HD 3000 only - unless you really know what you are doing!)
 - Note: The custom DSDT is based off BIOS v1.46 (flashed with whitelist mod or original)
 
 ### **STEPS**
 
 1. Download MacOS Mojave.app on App Store
 2. Partition USB Drive (GPT/USB/MacOSExtended)
 3. Create Bootable Drive With This Command --->
 ```
 sudo "/Applications/Install macOS Mojave.app/Contents/Resources/createinstallmedia" --volume /Volumes/USB
 ```
 4. Install Clover on the USB
  - Run espmount.bash to mount ESP on USB Drive
  - Copy the EFI directory to the ESP directory of the USB
  - Note: run "diskutil list" on the command line to find your USB and HD disk devices
 ```
 sudo mkdir /Volumes/ESP-USB
 sudo mount -t msdos /dev/disk1s1 /Volumes/ESP-USB
 cp -a ~/Downloads/Lenovo-T420-Clover-master/EFI/ /Volumes/ESP-USB/EFI
 ```
