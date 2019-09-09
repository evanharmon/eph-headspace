# UNIX LINUX SCRIPTS

## Summary

Notes on writing linux scripts

## Resources

[Linter](http://www.shellcheck.net)
[Single Quote Double Quote In Scripts](http://mywiki.wooledge.org/Quotes)

## Safe Way To Run Bash

```bash
#!/usr/bin/env bash
```

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

## Check If Last / Prior Command Errored

```bash
access_key_id=$(echo "$creds_json" | jq --exit-status --raw-output '.Credentials.AccessKeyId')
rv="$?"
if [[ $rv -ne 0 || ! $access_key_id ]]; then
    echo "$pkg: failed to parse output for access_key_id: $creds_json" 1>&2
    return "$rv"
fi
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

## Operators

equals

```bash
if [[ rv -eq 0 ]]; then
    echo "should not be 0" 1>&2
    return exit 1
fi
```

not equals

```bash
if [[ rv -ne 0 ]]; then
    echo "should be 0" 1>&2
    return exit 1
fi
```
