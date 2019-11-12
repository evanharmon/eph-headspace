# VISUAL STUDIO CODE

## Summary

## Resources

## Debug With GDB Server

[SO](https://stackoverflow.com/questions/53519668/how-to-attach-to-remote-gdb-with-vscode)

install `Native Debug` extension

## Settings File Location

macOS $HOME/Library/Application Support/Code/User/settings.json
Linux $HOME/.config/Code/User/settings.json

## Cmake / Debug Setup

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

## Open File In VSCode From Terminal

```console
code README.md
```

## View DotFiles

Toggle display of dotfiles (e.g., .env), Command-Shift-.
