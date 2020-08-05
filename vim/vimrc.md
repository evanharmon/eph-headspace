# MYVIMRC

## Summary

Notes on using \$MYVIMRC, init.vim, .vimrc

## Set Default Shell

`set shell=/bin/zsh`

## Check If Plugin / Command Exists

```
" after/plugin/speeddating.vim
if exists(':SpeedDatingFormat')
    SpeedDatingFormat %-d %B %Y
endif
```

## Set Terminal Scrollback Size In Neovim

```
set scrollback=100000
```
