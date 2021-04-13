# NEOVIM FZF

## Shorcut Mappings
```
nmap ; :Buffers<CR>
nmap <Leader>t :Files<CR>
nmap <Leader>r :Tags<CR>
```

## Install With Dein In $MYVIMRC
(https://github.com/Shougo/dein.vim/issues/74)

```
call dein#add('junegunn/fzf', { 'build': './install --all', 'merged': 0 })
call dein#add('junegunn/fzf.vim', { 'depends': 'fzf' })
```
