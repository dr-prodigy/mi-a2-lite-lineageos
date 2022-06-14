=================================================
Xiaomi Mi A2 Lite (Daisy) - Lineage OS 18.1 setup
=================================================

Complete procedure on how to set up Lineage OS 18.1 (Android 11) on a Xiaomi Mi A2 Lite smartphone updated to the last available stock firmware (MiUI) provided by Xiaomi.

I created this collecting miscellaneous info from the internet + reviewing, improving, and testing everything (a lot of outdated / wrong information are still around, so it took me some time).

It is mainly meant as a quick manual for my personal future reference, but I decided to share it to possibly help someone else willing to do the same.

As of now, it works for the provided fw/sw versions only, although you could find it suitable for other custom ROMs too with some small changes.

Whenever possible, I tried to use official and stable links, but there is no guarantee they will stay there for long / forever.

The procedure is provided as-is: don't expect it to be very detailed nor maintained. Please avoid asking for support and / or fixes.

IMPORTANT: either successful or not, the procedure involves COMPLETE STORAGE DELETION, so please back up everything you need prior to start.

**WARNING: NO RESPONSIBILITY FOR ANY DATA LOSS / PHONE BRICK / ANYTHING.. USE AT YOUR OWN RISK!**

*Procedure tested on: 2022-06-13*

Required packages
-----------------

- `MiUI stock ROM 10.0.3.0 <http://bigota.d.miui.com/V10.0.3.0.PDLMIXM/daisy_global_images_V10.0.3.0.PDLMIXM_20190114.0000.00_9.0_e8d8d4a6d0.tgz>`_

- `TWRP for Xiaomi Daisy <https://github.com/TWRP-Mi-A2-Lite/twrp_device_xiaomi_daisy/releases>`_

- `LineageOS 18.1 <https://forum.xda-developers.com/t/rom-and-microg-unofficial-11-0-lineage-os-18-1-xiaomi-a2-lite.4229439/>`_

- `MindTheGapps 11.0.0-arm64 <https://wiki.lineageos.org/gapps>`_

- `Magisk 24.1 or newer <https://magiskupdate.com/magisk-zip/>`_ (optional, for root)


First time installation
-----------------------

- Unlock bootloader (eg: https://www.thecustomdroid.com/unlock-bootloader-xiaomi-mi-a2-lite-guide/ )

- Enter fastboot (press Down+Power)

- Flash MiUI stock ROM v.10.0.3.0
    - unpack tgz stock ROM
    - run flash
        `flash_all.sh`

- Reboot to system

- Reboot to fastboot (press Down+Power)

- Boot to TWRP via fastboot
    `fastboot boot twrp-3.5.2_9-2-daisy-unofficial.img`

On TWRP:

- Format data

- Transfer ROM and TWRP zip to /sdcard
    `adb push [filename] /sdcard`

- Flash the ROM zip => saved to inactive boot slot

- Flash TWRP installer zip

- Reboot to recovery (TWRP) => switches to other boot slot

- Transfer Gapps and Magisk zip to /sdcard
    `adb push [filename] /sdcard`

- Flash Gapps

- Flash Magisk (Optional)

- Format data

- Reboot to system

\.\. et voila :-)

Useful commands
---------------
- boot from image
    `fastboot boot [img name]`
- reboot
    `fastboot reboot`
- copy files from PC to device while running TWRP:
    `adb push [filename] /sdcard`
- set boot slot
    `fastboot set_active [a|b]`
