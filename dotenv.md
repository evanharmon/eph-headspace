# DOTENV

## Summary

Notes on working with .env files

## NODEJS

### Reference .env config file by exact path

```
const path = require('path');
require('dotenv').config({ path: path.join(__dirname, '.env') }); // eslint-disable-line global-require
```

## CLI

### Load .ENV Files From CLI

```console
npm install -g dotenv-cli
```

```console
dotenv -- mvn exec:java -Dexec.args="-g -f"
```

## Load /Export .env Variables To Shell

[SO](https://stackoverflow.com/questions/19331497/set-environment-variables-from-file-of-key-pair-values)

```
set -o allexport; source .env; set +o allexport
```
