# setup network

Remote accessing the pi zeros will be essential for running kubenetes cluster.
We are using three different boards: raspberry pi zero w, banana pi zero m2, and orange pi zero.
Each board has a different chipset, operating system, and capabilities.
The details of the basic network setup for each board/operating system are detailed below.

# raspberry pi zero

* install 2020-08-20-raspios-buster-armhf-lite.img on sd card
  * [image](https://www.raspberrypi.org/downloads/raspberry-pi-os/)
* login as pi, raspberry

## Setup Network

```bash
passwd
# change password

raspi-config
# set hostname
# set wireless
```

# banana pi zero m2

* install Armbian_20.08.1_Bananapim2zero_focal_current_5.8.5.img on sd card
  * [image](https://www.armbian.com/bananapi-m2-zero/)
* login as root, 1234

## Setup Network

```bash
passwd
# change password

# wifi
nmcli dev wifi list
# use SID from list
nmcli device wifi connect <SSID|BSSID> password <password>

armbian-config
# set hostname
# set wireless
```

# orange pi zero

* install Armbian_20.08.1_Orangepizero_focal_current_5.8.5.img on sd card
* login as root, 1234

## Setup Network

```bash
# wifi
nmcli dev wifi list
# use SID from list
nmcli device wifi connect <SSID|BSSID> password <password>

armbian-config
# set hostname


# wifi on boot
sudo nano /etc/network/interfaces #Add at end of file

auto wlan0
iface wlan0 inet dhcp
wpa-ssid <SSID|BSSID>
wpa-psk <Password>

```

