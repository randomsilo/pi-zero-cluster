# Banana Pi BPI-M2 Zero H2+ [buy](https://www.amazon.com/gp/product/B07PVQQWP7)

> $35.37 + $2.99 Shipping

The Banana Pi M2 Zero is not as popular as the Raspberry Pi Zero W.
The pin outs are the same and the processor is much faster.

## Hardware

```
CPU: H2+ Quad-core Cortex-A7 H265/HEVC 1080P
GPU: Mali400MP2 GPU @600MHz,Supports OpenGL ES 2.0
Memory (SDRAM): 512M DDR3(shared with GPU)
Onboard Storage: TF card (Max. 64GB)
Onboard Network: NOPE
Onboard WIFI: SDIO AP6212（option AP6181、AP6335）
Video decoding: 1080p@60fps,H.264 Video encoding 1080p@30fps,H.264
Video input: A CSI input connector Camera
Video Outputs: mini HDMI 1.4,1080P@30fps, DHCP
Audio Output: Mini HDMI
Power Source: Micro USB with 5V/2A
USB 2.0 Ports: one USB 2.0 OTG
Buttons: Power Button, Reset Button:
Low-level peripherals: 40 Pins Header,compatible with Raspberry Pi 3
uart GPIO(1x3) pin: UART, ground
LED: Power led & Status led
IR: N/A
Supported OS: Android, Ubuntu, Debian, Rasberry Pi Image
Product size: 65mm x 30mm
Weight: 15g												
```

### Hardware List

* USB to USB mini Adapter (comes with board)
* HDMI mini to HDMI Adapter (comes with board)
* Power Cable (comes with board)
* USB Keyboard
* USB Mouse
* [SD Card](https://www.amazon.com/gp/product/B089DPCJS1) 
* [heat sink](https://www.amazon.com/gp/product/B01EE4W730)
* [wifi antenna](https://www.amazon.com/gp/product/B018R0IZYM)
* [usb hub](https://www.amazon.com/gp/product/B08D6F5Z34)

## Install Operating System

[Offical Instructions](http://wiki.banana-pi.org/Banana_Pi_BPI-M2_ZERO#Linux)

[Latest Images](http://forum.banana-pi.org/c/Banana-pi-BPI-M2/M2image?order=activity)

## Important Links

* [Wiki](http://wiki.banana-pi.org/Banana_Pi_BPI-M2_ZERO)

## Troubleshooting

* [No HDMI Display](http://forum.banana-pi.org/t/no-signal-on-screen/7242)
I bypassed this problem by using a different monitor the fixes in from this [articel](https://www.raspberrypi.org/forums/viewtopic.php?t=34061) did not work for me.
Later, I changed out my HDMI cable and it worked without modification.

* Temperature

A quick way to see the temperature of your bpi zero.

``` 
cat /sys/class/thermal/thermal_zone1/temp
```

* Time does set

```
sudo bash
/lib/systemd/systemd-timesyncd

systemctl status systemd-timesyncd
systemctl stop systemd-timesyncd
systemctl start systemd-timesyncd

journalctl -xe
```

