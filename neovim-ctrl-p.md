# NEOVIM CTRL P

## Purge Cache/Refresh With CtrlP Open
<F5>

## Clear Entire Cache
`:CtrlPClearCache`
Sometimes you have to manually delete the files from ~/.cache/ctrlp though

## Cycle Between Modes
<c-f>
<c-b>

## Switch to Filename Only Search Instead of Full Path
<c-d>

## Switch to Regexp Mode
<c-r>

## Navigate List Up And Down
<c-j>
<c-k>

## Navigate Paths
.. <return>

## Open File In Tab Or a Split
<c-t>, <c-v>, <c-x>

## Mark Multiple Files and Open
<c-z> on files
<c-o> open

## Bookmark Directory
`:CtrlPBookmarkDirAdd [cwd] [title]`

## Search Bookmark Dirs
`:CtrlPBookmarkDir`

## Create New File and Directories
<c-y>

## Delete Buffer
ctrl z to mark buffers to delete
<F7>

## Old CtrlP Vim Setup
```
" CTRLP
let g:ctrlp_working_path_mode = "ra"
let g:ctrlp_lazy_upate = 1
" Exclude .gitignore files
set wildignore+=*/tmp/*,*.so,*.swp,*.zip " MacOSX / Linux
set wildignore+=*\\tmp\\*,*.swp,*.zip,*.exe " Windows
let g:ctrlp_custom_ignore = {
  \ "dir": "\v[\/]\.(git|hg|svn|node_modules|bower_modules|dist$)$",
  \ "file": "",
  \ "link": "",
  \ }
let g:ctrlp_show_hidden = 1
```

## CtrlP AG Vim Setup
```
  " Use ag in CtrlP for listing files. Lightning fast and respects .gitignore
  " let g:ctrlp_user_command = 'ag %s -l --nocolor -g ""'

  " ag is fast enough that CtrlP doesn't need to cache
  " let g:ctrlp_use_caching = 0
```
