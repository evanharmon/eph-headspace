# RipGrep

## Summary

Notes on using the rip grep cli tool

## Resources

- [GH Repo](https://github.com/BurntSushi/ripgrep)
- [User Guide](https://github.com/BurntSushi/ripgrep/blob/master/GUIDE.md)

## Install

```console
brew install ripgrep
```

## Common Options

### Show Lines Surrounding Match

show line numbers as well
--context=5, -C=5

```console
rg 'convert to string' -C
```

## Show File Names Only

```console
rg --files 'history.replaceState' .
```

## Use ripgrep with FZF in zsh

### .zshrc

`export FZF_DEFAULT_COMMAND='rg --files --no-ignore --hidden --follow --glob "!.git/*"'`
