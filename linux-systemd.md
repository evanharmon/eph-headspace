# SYSTEMD
can shutdown short / long - running processes

## System Scripts
`/etc/systemd/system`

## User Package Scripts
`/usr/lib/systemd/system`

## Targets (Run Levels)
Run Level 0: runlevel0.target, poweroff.target
Run Level 1: runlevel1.target, rescue.target
Run Level 2,4: runlevel2.target, runlevel4.target, multi-user.target
Run Level 3: runlevel3.target, multi-user.target
Run Level 5: runlevel5.target, graphical.target
Run Level 6: runlevel6.target, reboot.target
emergency: emergency.target
