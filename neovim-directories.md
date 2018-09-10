# NEOVIM DIRECTORIES

## Open Window Explorer
`:Explore`

## Change Directory
`:cd dockerbuilds`

## Change Vim Directory To Currently Open File (All Of Vim)
% current file %:p full path %:p:h full path with head
`:cd %:p:h`

## Change Vim Directory To Currently Open File (Just That Window)
`:lcd %:p:h`

## Set Present Working Directory
`:pwd $HOME/code`

## Automatically Set Directory To Current File
set autochdir
### better option
autocmd BufEnter * silent! lcd %:p:h

## List Old Files
`:oldfiles`

## Select Single File To Edit From Old Files
`:e #<13`

## Select Multiple Files To Edit From Old Files
`:args #<2 #<13 #<99`

## Show Directory Contents
`:!ls`

## Get Full Path Of File
`:!ls %:p`
