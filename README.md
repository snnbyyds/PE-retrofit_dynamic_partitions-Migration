# PE-retrofit_dynamic_partitions-Migration
https://sourceforge.net/projects/sn-roms/files/PixelExperience-13/fajita/
For roms released after PixelExperience_fajita-13.0-20221111-0550-UNOFFICIAL.zip
# First time install
1. Be on the latest OOS 11!
2. Download vbmeta.img, boot.img, super_empty.img: 
https://sourceforge.net/projects/evolution-x/files/fajita/

3. Reboot to bootloader
4. Run the following to flash the new retrofit dynamic partitions boot image + recovery:
``` fastboot flash vbmeta_a vbmeta.img ```
``` fastboot flash vbmeta_b vbmeta.img ```
``` fastboot flash boot_a boot.img ```
``` fastboot flash boot_b boot.img ```
5. Erase the old android partitions with the following:
``` fastboot erase system_a ```
``` fastboot erase system_b ```
``` fastboot erase odm_a ```
``` fastboot erase odm_b ```
``` fastboot erase vendor_a ```
``` fastboot erase vendor_b ```
6. Boot to recovery
7. In recovery, choose Advanced -> Enter fastboot to enter fastbootd
8. Initialize the retrofit super partitions for each slot:
``` fastboot wipe-super super_empty.img ```
``` fastboot set_active other ```
``` fastboot wipe-super super_empty.img ```
``` fastboot set_active other ```
9. Choose Enter recovery to return to recovery
10. While in recovery, navigate to Apply update -> Apply from ADB
``` adb sideload rom.zip ```
12. Format data, reboot to system

# Coming from a non-retrofit build
1. Download boot.img, super_empty.img
2. Reboot to bootloader
3. Run the following to flash the new retrofit dynamic partitions boot image + recovery:
``` fastboot flash boot_a boot.img ```
``` fastboot flash boot_b boot.img ```
4. Erase the old android partitions with the following:
``` fastboot erase system_a ```
``` fastboot erase system_b ```
``` fastboot erase odm_a ```
``` fastboot erase odm_b ```
``` fastboot erase vendor_a ```
``` fastboot erase vendor_b ```
5. Boot to recovery
6. In recovery, choose Advanced -> Enter fastboot to enter fastbootd
7. Initialize the retrofit super partitions for each slot:
``` fastboot wipe-super super_empty.img ```
``` fastboot set_active other ```
``` fastboot wipe-super super_empty.img ```
``` fastboot set_active other ```
8. Choose Enter recovery to return to recovery
9. While in recovery, navigate to Apply update -> Apply from ADB
``` adb sideload rom.zip ```
10. Reboot to system
