# NEOVIM CTAGS

## Install
ubuntu/debian
`sudo apt-get install exuberant-ctags`

Mac
`brew install ctags`

## Generate CTags
`ctags -R --languages=c --exclude=".git" --exclude=log .`

## Generate CTags with bundled Libs
`ctags -R --languages=c --exclude=".git" --exclude=log . $(bundle list --paths)`

## Jump to definition
```
:tag ClassName
^]
```

## Jump back from definition
`^t`

## Preview definition
`^W }`

## See all definitions
`g]`

## Move to next definition (:tnext)
`:tn`

## Move to previous definition (:tprevious)
`:tp`

## List all definitions (:tselect)
`:ts`

## Generate jsctags for Javascript Files
```
$ find . \
    -type f \
    -iregex ".*\.js$" \
    -not \
    -path "./node_modules/*" \
    -exec jsctags {} -f \; |\
    sed '/^$/d' |\
    sort >\
    tags
```
