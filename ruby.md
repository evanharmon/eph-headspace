# RUBY

## Summary

Notes on working with Ruby

## Resources

[RBENV Ruby Manager](https://github.com/rbenv/rbenv)

## Ruby Version Manager

use `rbenv`

### Common Mac Install Errors

`Configure: error: C Compiler cannot create executables`

Have multiple versions of xcode installed? Make sure your xcode tools are set
to the standard path of `/Applications/Xcode.app/Contents/Developer`. See
[Doc](xcode-select.md)

### Commands

list ruby versions to install

```console
rbenv install -l
```

update list of available ruby versions - must be done manually

```console
cd ~/.rbenv/plugins/ruby-build
git pull
```

### Mac OS X

install

```console
brew install rbenv
```

upgrade

```console
brew upgrade rbenv ruby-build
```

doctor checkup

```console
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash
```

### Linux

install

```console
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-installer | bash
```

doctor checkup

```console
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash
```
