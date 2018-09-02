# UNIX LINUX SCRIPTS
[Linter](http://www.shellcheck.net)

## Running Scripts

### Run And Execute Commands From Current Shell Enviroment
```console
$ source ./script.sh
```

# Run script in new shell
`$ ./script.sh`

## Writing Scripts
[Single Quote Double Quote In Scripts](http://mywiki.wooledge.org/Quotes)

### If Statements
Safely check for multi word command
```bash
if [[ "command -v nvm" = nvm ]]; then
```

Safely check for negation of multi word command
```bash
if [[ ! "command -v nvm" = nvm ]]; then
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
