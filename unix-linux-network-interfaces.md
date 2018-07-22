# location
/etc/network/interfaces

# List active network interfaces
`$ ifconfig`
`$ ip`

# List all network interfaces
`$ ifconfig -a`
`$ ip a`

# Bring down a network interface
`$ sudo ifdown en1`

# Bring up a network interface
`$ sudo ifup en1`

# Give interface new IP address
## CIDR Block determines Submask
`$ sudo ifconfig en0 192.168.0.150/24`

# Add additional local loopback ip address
`$ sudo ifconfig lo0 alias 127.0.0.2 up`

# Automatically bring up interface on startup
# /etc/network/interfaces
auto lo

# Use DHCP for interface
# /etc/network/interfaces
iface en0 inet dhcp

# Enable wifi and set ssid / password
`$ chmod 0600 /etc/network/interfaces`
wpa_passphrase ssid password
vi /etc/network/interfaces # change ssid and wpa-psk

# restart an interface
`$ sudo ifup wlan0`

# Check IP ports
`$ /sbin/ifconfig`
or
`$ /sbin/ifconfig -a`
