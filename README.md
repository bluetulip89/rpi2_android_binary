# rpi2_android_binary
this repository contains nothing but the binaries created from peyo-hd anroid build package and is created by using the following repositories:
https://github.com/peyo-hd/local_manifests
https://github.com/peyo-hd/device_brcm_rpi2

to boot anroid on your rpi2 follow this instructions after cloning the repo:
# Prepare sd card
 Partitions of the card should be set-up like followings.
  p1 512MB for BOOT : Do fdisk, format as fat32
  p2 512MB for /system : Do fdisk, new primary partition, size 512M.
  p3 512MB for /cache  : Do fdisk, format as ext4
  p4 remainings for /data : Do fdisk, format as ext4
 
# Write system partition
  $ cd out/target/product/rpi2
  $ sudo dd if=system.img of=/dev/<p2> bs=1M
  
# Boot partition, kernel & ramdisk
  device/brcm/rpi2/boot/* to p1:/
  kernel/rpi/arch/arm/boot/zImage to p1:/
  out/target/product/rpi2/ramdisk.img to p1:/
  
  all credits go to @peyo-hd !
