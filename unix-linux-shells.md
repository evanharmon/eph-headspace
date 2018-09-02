# UNIX LINUX SHELLS

## Check What Shell is Being Used
`$ echo $0`

## Change Shell Preference
`$ chsh -s /bin/zsh`

## Get Date For Start Of Filename
```console
$ date +%Y%m%d%H%M%S
```
outputs 20150104085700 style format

## Create New File With Timestamp
`$ touch `date +%Y%m%d%H%M%S`-add-fields-idptable.js`

## Inheritance
env variables inherited by child processes
shell variables not inherited

## Assign Variable
`$ a=879`

## Reference Current Directory
`${PWD}`

## Assign Path To Variable
`$ Vf=./Container-Files/Vim-7.4.Tar.Bz2`

## Assign Command To A Variable
`$ a=`ls -la``

## Remove An Env Variable
`$ unset NODE_ENV`

## View Shell Variables
`$ set | less`

## View Env Variables
`$ env`
or
`$ printenv`

## Export Env Variable To Shell (Case Sensitive)
`$ export NVIM_TUI_ENABLE_TRUE_COLORS=1`

## Single Env Variable For Command
`$ CID=$(docker ps -lq)`

## Use Env Variable In Command Line
`$ docker stats $CID`

## Command Substitution
Pipe output to a variable
`$ var4=$(aws ec2 describe-vpcs)`
fancy
`$ stackid=$(cat test.log|jq '.Stacks[0].StackId')`

## Mix Shell Variables And Text In Command Line
`$ aws s3 cp testfile.txt ${BUCKET}base/{FILE}`

## Script Date in New Date().toJSON() Format
`$ date -u +"%FT%T.000Z"`

## Show History File By Env Var
`$ echo $HISTFILE`

## Echo Without A Newline Added
`$ printf $FILE_SYSTEM_ID`

## Base64 Decode From STD IN
`$ echo QWxhZGRpbjpvcGVuIHNlc2FtZQ | base64 -D`

## Check If Script Eval Commands Are Available
Like `nvm` or `pyenv`
```console
command -v nvm
```

## Get Base Name Of A File From Full Path
`$ basename /home/user/file.sh`

