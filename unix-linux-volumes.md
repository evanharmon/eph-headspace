# Check if a volume has data
`$ file -s /dev/xvdf`

# Format
`$ mkfs -t ext4 /dev/xvdf`

# Mount to a folder
`$ mount /dev/xvdf /fileserver`

# Unmount
`$ unmount /dev/xvdf`
