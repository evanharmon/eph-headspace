# NEOVIM CTAGS

## Summary

notes on using CTAGS with neovim

## Resources

[Blog 09/2018](https://jdhao.github.io/2018/09/28/nvim_tagbar_install_use/)
[Neovim Ctags overview](https://github.com/neovim/neovim/wiki/Code-overview)

## Install

ubuntu/debian build from github

```console
git clone https://github.com/universal-ctags/ctags.git
cd ctags
./autogen.sh
./configure --prefix=/where/you/want/to/install # install to where you have access
make -j && make install # may require extra privileges depending on where to install
```

Mac

```console
brew install --HEAD universal-ctags/universal-ctags/universal-ctags
```

## Generate CTags

`ctags -R --languages=c --exclude=".git" --exclude=log .`

## Generate CTags with bundled Libs

`ctags -R --languages=c --exclude=".git" --exclude=log . $(bundle list --paths)`

## Add Home Library Ctags

vimrc or vim command line

```
set tags+=~/JUCE/tags
```

## Jump to definition

```
<CTRL-]>
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
