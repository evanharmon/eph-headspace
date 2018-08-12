# NODE NVM

## Install on Cloud boxes issues
1. Installing nvm as a user instead of admin
2. NVM has a part that needs to use `export` and shell variables. This is
  really tricky depending on the build tool. Probably easier with docker.. not
  sure on ansible

## Install
```
curl -o- \
  https://raw.githubusercontent.com/creationix/nvm/v0.33.4/install.sh | \
  bash
```
