# RASPBERRY PI HEADLESS SETUP

## Summary

Notes on setting up a raspberry pi headless

## Resources

- [Official WiFi Setup](https://www.raspberrypi.org/documentation/configuration/wireless/headless.md)
- [Wireless Docs](https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md)
- [Raspbian Images](https://downloads.raspberrypi.org/raspbian/images)
- [Etcher For Flashing SD cards](https://www.balena.io/etcher/)
- [Remote Access Ip Address](https://www.raspberrypi.org/documentation/remote-access/ip-address.md)
- [SSH Wifi Setup](https://desertbot.io/blog/headless-raspberry-pi-4-ssh-wifi-setup)
- [PiBakery Download](https://www.pibakery.org/download.html)

## Setup OS On microSD

the microSD card will need to be flashed and setup with an OS
The NOOB out of the box setup isn't helpful when no monitor / keyboard / mouse
is being used.

Follow the instructions for [PiBakery](https://www.pibakery.org/docs/create.html)

## Enable SSH

create empty ssh file in root directory of microSD

```console
touch ssh
```

## Enable WIFI

create a file in root directory of microSD named `wpa_supplicant.conf` with the contents

if ssid is hidden, add line `scan_ssid=1` below `ssid=`

```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=US

network={
    ssid="NETWORK-NAME"
    psk="NETWORK-PASSWORD"
}
```

## Login Over WIFI

```console
ssh-keygen -R raspberrypi.local
ssh pi@raspberrypi.local
```

password should be `raspberry`
