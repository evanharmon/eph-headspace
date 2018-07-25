# NEOVIM DEIN

## Setup
Note choice of installation directory, it will be referenced in the init.vim file
```
$ curl https://raw.githubusercontent.com/Shougo/dein.vim/master/bin/installer.sh > installer.sh
$ sh ./installer.sh {specify the installation directory}
```
Open Neovim
Run `:UpdateRemotePlugins`
Close nvim and reopen

# Install
`:call dein#install()`

# Check for Updates
`:call dein#check_update()`
