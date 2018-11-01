# ITERM

## Fix Ctrl H backspace issue
```console
infocmp $TERM | sed 's/kbs=^[hH]/kbs=\\177/' > $TERM.ti
tic $TERM.ti
```

## Alt-C Prints Out ç
[](https://github.com/junegunn/fzf/issues/164)
Press `ESC` then `c` instead

## Mojave Full Disk Access
In OS X, under `system preferences`, select `Security & Privacy`, choose the
`privacy` tab, and select the `Full Disk Access` option in the list. Use the
keychain icon marked `Click the lock to make changes`. Use the `+` button to
add an application. In the dropdown window that appears, navigate to the 
`Applications` folder and select `iTerm`

## Mojava Accessibility Feature Access
In OS X, under `system preferences`, select `Security & Privacy`, choose the
`privacy` tab, and select the `Accessibility` option in the list. Use the
keychain icon marked `Click the lock to make changes`. Use the `+` button to
add an application. In the dropdown window that appears, navigate to the 
`Applications` folder and select `iTerm`
