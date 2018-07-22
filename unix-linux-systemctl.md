# General
used to control systemd

# show what systemd is using
`$ systemctl`

# Check status of a systemd script
`$ sudo systemctl status sound.target`

# start a systemd script
`$ sudo systemctl start sound.target`

# stop a systemd script
`$ sudo systemctl stop sound.target`

# enable a target / run level
`$ sudo systemctl enable multi-user.target`

# set default run level
`$ sudo systemctl default multi-user.target`
