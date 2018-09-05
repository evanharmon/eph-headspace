# SYSTEMCTL
used to control systemd

## Show What Systemd Is Using
```console
$ systemctl
```

## Check Status Of A Systemd Script
```console
$ sudo systemctl status sound.target
```

## Start A Systemd Script
```console
$ sudo systemctl start sound.target
```

## Stop A Systemd Script
```console
$ sudo systemctl stop sound.target
```

## Enable A Target / Run Level
```console
$ sudo systemctl enable multi-user.target
```

## Set Default Run Level
```console
$ sudo systemctl default multi-user.target
```
