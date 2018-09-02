# NVM
(https://github.com/creationix/nvm)

## Install
on MacOS, requires xcode command line tools to be installed
```console
VERSION=v0.33.11
curl -o- \
  https://raw.githubusercontent.com/creationix/nvm/$VERSION/install.sh | \
  bash
```

## Script To Add To Bash / ZSH
```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```
or this version to avoid nvm use being called on shell load
```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh --no-use"
```
