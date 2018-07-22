# LINUX PERMISSIONS

[Handy Permissions Calculator](http://permissions-calculator.org/)

## Test Folder / File Permissions As Diff User
`$ sudo -u {user} ls /usr/local/var/run`

## Change Permissions Recursively
`$ chmod -R`

CHMOD
u = user, g = group, o = others
r = read, w = write, x = execute
## Add User Execute Permissions
## Make Executable
`$ chmod u+x script.sh`

## CHOWN Change Owner
`$ chown dev package.json`

## Change Group Permissions
`$ chgrp root package.json`

## Change Owner And Group
`$ chmod dev:dev package.json`

## .ssh folder
700 (drwx------)

## Public key (.pub) files
644 (-rw-r--r--)

## Private key files
600 (-rw-------)

## User Directory should be not writeable by group or other
`$ chmod go-w ~`
