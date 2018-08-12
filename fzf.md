# FZF

## ZSHRC Setup
`[ -f ~/.fzf.zsh ] && source ~/.fzf.zsh`

### fzf via Homebrew
```
if [ -e /usr/local/opt/fzf/shell/completion.zsh ]; then
  source /usr/local/opt/fzf/shell/key-bindings.zsh
  source /usr/local/opt/fzf/shell/completion.zsh
fi
```

### fzf via local installation
```
if [ -e ~/.fzf ]; then
  _append_to_path ~/.fzf/bin
  source ~/.fzf/shell/key-bindings.zsh
  source ~/.fzf/shell/completion.zsh
fi
```
