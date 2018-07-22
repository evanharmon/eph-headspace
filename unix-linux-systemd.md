# System scripts
/etc/systemd/system

# Package scripts
/usr/lib/systemd/system

# Targets
## act like run levels
Run Level 0: runlevel0.target, poweroff.target
Run Level 1: runlevel1.target, rescue.target
Run Level 2,4: runlevel2.target, runlevel4.target, multi-user.target
Run Level 3: runlevel3.target, multi-user.target
Run Level 5: runlevel5.target, graphical.target
Run Level 6: runlevel6.target, reboot.target
emergency: emergency.target

# SystemD can shutdown short / long - running processes
