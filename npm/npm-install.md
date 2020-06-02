# NPM INSTALL

## Summary

Notes on installing npm modules / packages via the CLI

## Resources

- [NPM Docs](https://docs.npmjs.com/)

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

## Check For Missing Peer Dependencies

```console
npm ls --depth=0
```

## Upgrade Npm Module

```console
npm install -D graphql@latest
```

## Install Packages Without Package.json

```console
cd src && npm init --yes && npm install redis && rm package.json package-lock.json && cd ..
```
