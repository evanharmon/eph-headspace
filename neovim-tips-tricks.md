# NEOVIM TIPS AND TRICKS

## Summary

Tips and tricks on using Neovim

## STABLE Install (Brew)

```console
brew install neovim/neovim/neovim
```

## STABLE Upgrade

```console
brew update
brew upgrade neovim
```

## DEV Install

```console
brew tap neovim/neovim
brew install --HEAD neovim
```

## DEV Upgrade

```console
brew update
brew reinstall --HEAD neovim
```

## PIP plugin

```console
pip install --user neovim
```

## Add Dein to NVIM Plugin Settings

with neovim open, :UpdateRemotePlugins

## VIMPLUG

if install fails with github:: its probably a mispelled plugin name in VIMRC

## Pretty Print Json

```console
:%!python -m json.tool
```

## Exit Terminal Mode

<C-\><C-n>
Keybound to <leader>e in my setup

## Open File Read Only

```console
:view /path/to/file
```

### CLI

```console
vim -M /path/to/file (DOES NOT WORK IN NVIM)
```

## VIM tar bzip2 Error

Log in as user instead of root make sure bzip2 installed

## Check File Type

```console
:set ft?
```

## Get Full Path of Current File

```console
:echo @%
```

## Open File From Import Statement

gf

## Shortcut For Exiting Terminal Mode

tnoremap <leader>e <C-\><C-n> " exit terminal mode to normal mode in NVIM

## Deoplete Failed to Load

```console
:UpdateRemotePlugins
```

## Enter Insert Mode When Switching Back to Terminal Window

autocmd BufWinEnter,WinEnter term://\* startinsert

## Install All Plugins Headless

```console
nvim --headless +PlugInstall +UpdateRemotePlugins +qall
```
