# MAC BASH

## Summary

Notes on specific bash /zsh commands to use on Mac OSX compared to standard linux

## Resources

### Clipboard

#### Copy File

```console
cat .env | pbcopy
```

#### Paste To File

```console
pbpaste > .env
```

### User Management

#### Get User Info

substitute for `getent`

```console
dscacheutil -q user -a name evan
```
