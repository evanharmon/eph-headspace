# FZF MARKER

# Summary
Notes on installing and using Marker

## Resources
[GITHUB](https://github.com/pindexis/marker/blob/master/README.md)
[OSX ISSUES](https://apple.stackexchange.com/questions/24632/is-it-safe-to-upgrade-bash-via-homebrew/24635#24635)

## OS X BASH
OS X has an older version of bash. Has to be updated.

```bash
brew install bash
sudo -- sh -c "echo '/usr/local/bin/bash' >> /etc/shells"
```

## Default Command Shortcuts
Ctrl-space: search for commands that match the current written string in the command-line.
Ctrl-k (or marker mark): Bookmark a command.
Ctrl-t: place the cursor at the next placeholder, identified by '{{anything}}'
`marker remove`: remove a bookmark
