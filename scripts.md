# UNIX LINUX SCRIPTS
[Linter](http://www.shellcheck.net)

## Running Scripts

Run And Execute Commands From Current Shell Enviroment
```console
source ./script.sh
```

Run script in new shell
```console
./script.sh
```

## Writing Scripts
[Single Quote Double Quote In Scripts](http://mywiki.wooledge.org/Quotes)

### Options
Echo commands with interpolation
```bash
set -x
```

Exit early if pipeline returns non-zero code
```bash
set -e
```

Exit early if pipeline returns non-zero code

### If Statements
Safely check for multi word command
```bash
if [ -x "$(command -v yarn)" ]; then
```

### Script Error Unary Operator Expected
Double quote your variables!
```bash
"$IP"
```

### Abort On First Error
```bash
#!/bin/bash
set -e

/bin/command-that-fails
/bin/command-that-fails2
```

## Check If Folder Exists And Remove
```bash
DIR=/tmp/dir.lock
if [ -d "$DIR" ]; then
    printf '%s\n' "Removing Lock ($DIR)"
    rm -rf "$DIR"
fi
```

## Variables

#### Set Default Variables
```bash
BUCKET="${BUCKET:-mydefaultvalue}"
```

#### Set Current Directory Name With Only Basename
```bash
CURR_DIR="${CURR_DIR:-${PWD##*/}}"
```

## Parameters

#### Append / Pass parameters from script call
```bash
aws s3 cp . s3://$BUCKET "${@}"
```
