# NPM INSTALL

## Summary

Notes on installing npm modules / packages via the CLI

## Install Specific Version

```console
npm install {package}@{version}
```

## Install Private Module

```console
npm install @company/private-package
```

## Install Module From Github

```console
npm install git://github.com/evanharmon/eslint-config-harmonsoft
```

## Speed Up In production

```console
npm install --production
```

## Output Only Whats Necessary For Logging

```console
npm install --loglevel warn
```

## Install As Continuous Integration

```console
npm ci
```

## Permissions Issues Docker As Root

install with flags to fix this issue

```console
npm install --global pure-prompt --allow-root --unsafe-perm=true
```

## Install Globally And Link

```console
npm install -g @wdio/cli
npm link @wdio/cli
```

## Xcode Dependencies

some npm packages need xcode tools, to install them run:

```console
xcode-select --install
```
