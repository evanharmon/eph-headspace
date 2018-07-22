# Check What Shell is Being Used
`$ echo $0`

# Change shell preference
`$ chsh -s /bin/zsh`

# get date for start of filename
date +%Y%m%d%H%M%S
outputs 20150104085700 style format

# create new file with timestamp
`$ touch `date +%Y%m%d%H%M%S`-add-fields-idptable.js`

# Inheritance
env variables inherited by child processes
shell variables not inherited

# Remove an ENV variable
`$ unset NODE_ENV`

# View Shell Variables
`$ set | less`

# View Env Variables
`$ env`
or
`$ printenv`

# Export Env Variable to Shell (case sensitive)
`$ export NVIM_TUI_ENABLE_TRUE_COLORS=1`

# Single Env Variable For Command
`$ CID=$(docker ps -lq)`

# Use Env Variable In Command Line
`$ docker stats $CID`

# Command Substitution
## Pipe output to a variable
`$ var4=$(aws ec2 describe-vpcs)`
## fancy
`$ stackid=$(cat test.log|jq '.Stacks[0].StackId')`

# Mix Shell variables and text in command line
`$ aws s3 cp testfile.txt ${BUCKET}base/{FILE}`

# Script Date in new Date().toJSON() format
`$ date -u +"%FT%T.000Z"`

# Show History file by env var
`$ echo $HISTFILE`

# Echo without a newline added
`$ printf $FILE_SYSTEM_ID`

# Base64 decode from STD IN
`$ echo QWxhZGRpbjpvcGVuIHNlc2FtZQ | base64 -D`
