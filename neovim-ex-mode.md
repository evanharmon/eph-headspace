# NEOVIM EX MODE

## Summary

Notes on using neovim's execute mode

## Copy

:t address

## Move

:m address, address

## Copy word under cursor

<C-R><C-W>

## Paste in command line

<C-R>"

## Add comma at end

`:'<,'>norm A,`

# Delete Range of Lines

`:53,105d`

## Repeat macro over range of lines

`:5,10norm! @q`

## Execute command from shell

:!cmd

## Send File to Shell as Commands

`:write !sh`

## Sort Part of a CSV file

`:2,$!sort -t',' -k2`

## Execute command and insert stdout at cursor

`:read !ls ./rules`

# Norm delete all characters after certain line

## ex: v.search.results.test = res.data;

`:%norm f=C`

# Replace space indents with tabs

## if no tabstop set or its set to expandtab then replace tabs with spaces

`:retab`

# Copy command to system clipboard

## Steps: bring up command history, j/k to select line, copy using system clipboard

q:
"+yy

# Copy search to system clipboard

## Steps: bring up search history, j/k to select line, copy using system clipboard

q/
"+yy

# Get Count of search

`%s/TestPhrase//gn`
