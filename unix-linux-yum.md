# Package manager for:
amazon linux, centos

# List Package Install
`$ yum list sudo`

# List ALL Installed Packages
`$ yum list installed`

# Find Package
`$ yum search vim`

# Check for updates - dry run
`$ yum check-update`

# Install RPM's on Amazon Linux
https://aws.amazon.com/premiumsupport/knowledge-center/ec2-enable-epel/
`$ vim /etc/yum.repos.d/repel.repo`
change enabled=0 to enabled=1
BETTER METHOD
`$ sudo yum-config-manager --enable epel`
