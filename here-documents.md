# HERE DOCUMENTS

## Summary

Notes on using `here documents` for generated content

## Resources

[Guide](http://tldp.org/LDP/abs/html/here-docs.html)

## Don't Interpolate Variable

[SO](https://stackoverflow.com/questions/4937792/using-variables-inside-a-bash-heredoc)

use a `\`

```bash
local=$(uname)
ssh -t remote <<EOF
    echo "$local is the value from the host which ran the ssh command"
    # Prevent here doc from expanding locally; remote won't see backslash
    remote=\$(uname)
    # Same here
    echo "\$remote is the value from the host we ssh:ed to"
EOF
```
