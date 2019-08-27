# UNIX LINUX SHELLS

## Check What Shell is Being Used

```console
echo $0
```

## Change Shell Preference

```console
chsh -s /bin/zsh
```

## Get Date For Start Of Filename

```console
date +%Y%m%d%H%M%S
```

outputs 20150104085700 style format

## Create New File With Timestamp

```console
touch date +%Y%m%d%H%M%S`-add-fields-idptable.js`
```

## Inheritance

env variables inherited by child processes
shell variables not inherited

## Assign Variable

```console
a=879
```

## Reference Current Directory

```console
${PWD}
```

## Assign Path To Variable

```console
Vf=./Container-Files/Vim-7.4.Tar.Bz2
```

## Assign Command To A Variable

```console
a=ls -la``
```

## Remove An Env Variable

```console
unset NODE_ENV
```

## View Shell Variables

```console
set | less
```

## View Env Variables

`env`
or
`printenv`

## Export Env Variable To Shell (Case Sensitive)

```console
export NVIM_TUI_ENABLE_TRUE_COLORS=1
```

## Single Env Variable For Command

```console
CID=$(docker ps -lq)
```

## Use Env Variable In Command Line

```console
docker stats $CID
```

## Command Substitution

Pipe output to a variable

```console
var4=$(aws ec2 describe-vpcs)
```

fancy

```console
stackid=$(cat test.log|jq '.Stacks[0].StackId')
```

## Mix Shell Variables And Text In Command Line

```console
aws s3 cp testfile.txt ${BUCKET}base/{FILE}
```

## Script Date in New Date().toJSON() Format

```console
date -u +"%FT%T.000Z"
```

## Show History File By Env Var

```console
echo $HISTFILE
```

## Echo Without A Newline Added

```console
printf $FILE_SYSTEM_ID
```

## Base64 Decode From STD IN

```console
echo QWxhZGRpbjpvcGVuIHNlc2FtZQ | base64 -D
```

## Check If Script Eval Commands Are Available

Like `nvm` or `pyenv`

```console
command -v nvm
```

## Get Base Name Of A File From Full Path

```console
basename /home/user/file.sh
```

## Get Name Of Current Folder

```console
basename "$PWD"
```

## Convert Decimal To Hex

```sh
printf "%X\n" 1675637
```

## Set Variable On Command Line And Use In Command

```console
PROJECT_DIR="$(basename "$PWD")"; echo "$PROJECT_DIR"
```

## Avoid Duplicating \$PATH Entries Between Bash & Zsh

```console
if [[ ":$PATH:" != *":/usr/local/go/bin:$GOPATH/bin:"* ]]; then
    export PATH=/usr/local/go/bin:$GOPATH/bin:$PATH
fi
```

## Check What Shell Is Being Used

helpful to check for /bin/dash on debian, etc

```console
readlink -f $(which sh)
```
