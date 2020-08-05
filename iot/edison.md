# INTEL EDISON

## Connect via Terminal
`$ screen {tty.usb} 115200`

## Logout / Disconnect
CTRL + A
CTRL + D

## Restart
hold button for 4 seconds

## Reset
hold button for 8 seconds

## SSH in
`$ ssh root@10.0.0.59`

## Default user / passwords
jubilinux boots with two default users: root and edison. Both users’ passwords
are edison. Be sure to change both passwords

## Change Basic Config
`$ vi /etc/rc.local`

## Switch from WIFI to access point
```
systemctl stop wpa_supplicant
systemctl start hostapd
```

## Delete contents of Edison Drive
`$ rm -rf * && rm -rf \.*`

## Install Tools
MAC: `brew install dfu-util coreutils gnu-getopt`
LINUX: `sudo apt-get install dfu-util`

## FLASH
Download Latest Image, CD in to the folder and run
`$ ./flashall.sh`
