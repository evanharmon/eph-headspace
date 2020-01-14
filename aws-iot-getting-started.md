# AWS IOT GETTING STARTED

## Summary

Notes on getting started with AWS IoT

## Resources

- [Getting Started Tutorial - RaspberryPi](https://docs.aws.amazon.com/greengrass/latest/developerguide/setup-filter.rpi.html)

## OS Setup

### Add User And Group

```console
sudo adduser --system ggc_user
sudo addgroup --system ggc_group
```

### OS Protections

#### Enable Hardlink / Softlink OS Protection

```console
sudo su
vi /etc/sysctl.d/98-rpi.conf
```

add the below lines to the file

```
fs.protected_hardlinks = 1
fs.protected_symlinks = 1
```

```console
sudo reboot
```

confirm protections

```
sudo sysctl -a 2> /dev/null | grep fs.protected
```

## Lambda Setup

### Enable CGroups

```console
sudo vi /boot/cmdline.txt
```

Append the following to the end of the existing line, not as a new line.

```
cgroup_enable=memory cgroup_memory=1
```

```console
sudo reboot
```
