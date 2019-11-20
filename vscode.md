# VISUAL STUDIO CODE

## Summary

## Resources

[DOCS Integrated Terminals](https://code.visualstudio.com/docs/editor/integrated-terminal)
[Master The Terminal](https://www.growingwiththeweb.com/2017/03/mastering-vscodes-terminal.html)

## Open File In VSCode From Terminal

```console
code README.md
```

## View DotFiles

Toggle display of dotfiles (e.g., .env), Command-Shift-.

## Setup

### Settings.json

#### Settings File Location

- macOS \$HOME/Library/Application Support/Code/User/settings.json
- Linux \$HOME/.config/Code/User/settings.json

#### MAC OS X

The default `settings.json` and `launch.json` are stored deep inside the $HOME
directory in the Library folder. Very annoying. Symlink them to $HOME

```console
ln -sf ~/.config/vscode/launch.json ~/Library/Application\ Support/Code/User/launch.json
ln -sf ~/.config/vscode/settings.json ~/Library/Application\ Support/Code/User/settings.json
ln -sf ~/.config/vscode/extensions.json ~/Library/Application\ Support/Code/User/extensions.json
```

#### Linux

### Launch.json

### Cmake / Debug Setup

```json
"cmake.debugConfig": {
    "stopAtEntry": false,
    "MIMode": "lldb",
    "miDebuggerPath": "/Users/eharmon/.vscode/extensions/ms-vscode.cpptools-0.26.0/debugAdapters/lldb/bin/lldb-mi",
    "logging": {
        "trace": true,
        "engineLogging": true,
        "traceResponse": true
    }
}
```

## Debugging

remember to copy over arguments from `task.json` to launch file if trying to
debug CLI tools

### Debug With GDB Server

[SO](https://stackoverflow.com/questions/53519668/how-to-attach-to-remote-gdb-with-vscode)

install `Native Debug` extension

## TERMINAL

### Rename Terminal Session

run the command `terminal rename`
