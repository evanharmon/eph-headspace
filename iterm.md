# ITERM

## Fix Ctrl H backspace issue
```
infocmp $TERM | sed 's/kbs=^[hH]/kbs=\\177/' > $TERM.ti
tic $TERM.ti
```

## Alt-C Prints Out ç
(https://github.com/junegunn/fzf/issues/164)
Press `ESC` then `c` instead
