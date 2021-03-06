# Arch Linux for PinePhone
Installation scripts to deploy Arch Linux ARM to PinePhone.

Arch Linux uses a manual installation process via a command line. Combined with installing on a smartphone this can become a demanding task. The aim of this repository is to provide guidance and automation. You can more easily prepare a usable PinePhone OS while still being able to customize it to the maximum.

# Usage
You'll find several shell scripts that should be executed in a given sequence. Some are mandatory, some are purely optional. Pick and choose what **you** want to build!

| Script Name          | Mandatory?  | Description |
|:-------------------- |:-----------:| ----------- |
| 00-sanity_check.sh   | Recommended | Checks that your build environment meets all the requirements: necessary tools, permissions etc.
| 01-download.sh       | Yes         | Downloads all the required components: rootfs, kernel, bootloader.
| 02-format_sdcard.sh  | Yes, once   | Prepares a partition table on your SD Card and formats it.
| 03-flash_rootfs.sh   | Yes, once   | Populates the SD Card's root partition with the root filesystem.
| 04-flash_kernel.sh   | Yes         | Populates the SD Card's boot partition with a bootloader and a kernel.
| 10-usb_network.sh    | Recommended | Configures a USB network interface on both the SD Card and the host system.
| 11-passwordless_ssh  | Recommended | Installs your SSH public key as an authorized key for passwordless SSH login.
| ...                  | ...         | ...
| 99-cleanup.sh        | Optional    | Removes previously downloaded files and does a cleanup after any failures.
 
# Current Status
All of the above scripts are implemented apart from:
* 11-passwordless_ssh

# Sources
* https://archlinuxarm.org/platforms/armv8/allwinner/pine64
* https://xnux.eu/howtos/install-arch-linux-arm.html
