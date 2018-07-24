# UBILINUX
[jubilinux](http://www.jubilinux.org/)
[SparkFun Tutorial](https://learn.sparkfun.com/tutorials/loading-debian-ubilinux-on-the-edison)

## Edison Flashing
http://openaps.readthedocs.io/en/latest/docs/Resources/Edison-Flashing/all-computers-flash.html

## Install Nodejs
```
$ curl -sL https://deb.nodesource.com/setup_8.x | bash -
$ dpkg -P nodejs nodejs-dev
$ apt-get update && apt-get -y dist-upgrade && apt-get -y autoremove
$ apt-get install -y sudo strace tcpdump screen acpid vim python-pip locate

$ adduser edison sudo
$ adduser edison dialout
$ dpkg-reconfigure tzdata # Set local time-zone
```
