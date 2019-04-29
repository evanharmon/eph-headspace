# FZF

[tips](https://mike.place/2017/fzf-fd/)

## Install Via Homebrew

```bash
$ brew install fzf
$ /usr/local/opt/fzf/install
```

## ZSH

### Setup

```bash
[ -f ~/.fzf.zsh ] && source ~/.fzf.zsh
export FZF_DEFAULT_COMMAND="fd . $HOME"
export FZF_CTRL_T_COMMAND="$FZF_DEFAULT_COMMAND"
export FZF_ALT_C_COMMAND="fd -t d . $HOME"
```

### FZF ZSH Setup Via Homebrew

```
if [ -e /usr/local/opt/fzf/shell/completion.zsh ]; then
  source /usr/local/opt/fzf/shell/key-bindings.zsh
  source /usr/local/opt/fzf/shell/completion.zsh
fi
```

### FZF ZSH Setup Via local installation

```
if [ -e ~/.fzf ]; then
  _append_to_path ~/.fzf/bin
  source ~/.fzf/shell/key-bindings.zsh
  source ~/.fzf/shell/completion.zsh
fi
```

## USE

Change Directory
`ESC` + `c` then fuzzy type directory, then press `return`

## Fix Problems With Escape Key And ZSH VIM Mode

[Github Issue Fix](https://github.com/junegunn/fzf/issues/164)
change iterm profile, keys, option key settings to `esc+` for left and right options keys
