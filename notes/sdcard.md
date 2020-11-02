# sdcard

Raspberry pi, banana pi, and orange pi all use sd cards for their operating system.
Use these instructions to put an image onto an SD card.

## Linux Image Setup

### Identify USB Drive

```bash
# run with out usb sd card carrier
lsblk

# run with usb sd card carrier
lsblk

mmcblk0     179:0    0  29.7G  0 disk 
└─mmcblk0 179:1    0  29.7G  0 part /media/randomsilo/3566-3834

```

### Install Image

```bash

# start copy
cd /shop/randomsilo/maker/canary/device/sdcard
sudo dd bs=4M if=2020-05-27-raspios-buster-armhf.img of=/dev/mmcblk0 conv=fsync

# open new terminal
# check progress
sudo dd bs=4M if=2020-05-27-raspios-buster-armhf.img of=/dev/mmcblk0 status=progress conv=fsync

#confirm image

# copy file off of sd card
sudo dd bs=4M if=/dev/mmcblk0 of=from-sd-card.img 

# dd copies full disk, truncate both images so we can compare
sudo truncate --reference 2020-05-27-raspios-buster-armhf.img from-sd-card.img

# compare with diff
sudo diff -s 2020-05-27-raspios-buster-armhf.img from-sd-card.img

# should see
Files 2020-05-27-raspios-buster-armhf.img and from-sd-card.img are identical

# sync before unplugging drive
sync

# pull USB Carrier
# put SD Card into RPI
```

## Windows Image

[balenaEtcher](https://www.balena.io/etcher/)

* Install the application
* Select the zip file or image file
* Select Target (the SD Card)
* Click Flash

Turn off validation.

## Configure as Workstation

Plug in a monitor, USB hub, keyboard, mouse, and power cable.
Boot the RPI device and use the wireless icon in the upper right to connect the device to your local network.

## canary images

A canary image has been configured with all the device software and utilities in order to connect to the canary server.
These images are used to quickly setup new devices.
Look in the canary directory for the latest image.


