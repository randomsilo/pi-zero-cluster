# wifi

## Armbian Setup

```bash
nmcli dev wifi list

# use SID from list
nmcli device wifi connect <SSID|BSSID> password <password>
```