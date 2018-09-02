# SED

## Find and Replace
`$ sed -i .bak 's/hello/bonjour/' file.txt`

## Find And Replace In A File From Shell Command
`$ sed -i 's/REPLACE_WITH_INSTANCE_IP/'$INSTANCE_IP'/g' /tmp/init-cluster.sh`

## Print First 10 Lines Of File
Emulates `head`
`$ sed 10q`

## Print First Line Of File
Emulates `head -1`
`$ sed q`
