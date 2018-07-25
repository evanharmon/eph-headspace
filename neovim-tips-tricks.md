# NEOVIM TIPS AND TRICKS

## STABLE Install (Brew)
`$ brew install neovim/neovim/neovim`

## STABLE Upgrade
```
$ brew update
$ brew upgrade neovim
```

## DEV Install
```
$ brew tap neovim/neovim
$ brew install --HEAD neovim
```

## DEV Upgrade
```
$ brew update
$ brew reinstall --HEAD neovim
```

## PIP plugin
`$ pip install --user neovim`

## Add Dein to NVIM Plugin Settings
with neovim open, :UpdateRemotePlugins

## VIMPLUG
if install fails with github:: its probably a mispelled plugin name in VIMRC

## Pretty Print Json
`:%!python -m json.tool`

## Exit Terminal Mode
<C-\><C-n>
Keybound to <leader>e in my setup

## Open File Read Only
`:view /path/to/file`
### CLI
`$ vim -M /path/to/file (DOES NOT WORK IN NVIM)`

## VIM tar bzip2 Error
Log in as user instead of root make sure bzip2 installed

## Check File Type
`:set ft?`

## Get Full Path of Current File
`:echo @%`

## Open File From Import Statement
gf

## Shortcut For Exiting Terminal Mode
tnoremap <leader>e <C-\><C-n>                " exit terminal mode to normal mode in NVIM

## Deoplete Failed to Load
`:UpdateRemotePlugins`

## Enter Insert Mode When Switching Back to Terminal Window
autocmd BufWinEnter,WinEnter term://* startinsert
