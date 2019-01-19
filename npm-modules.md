# NPM MODULES

## Summary
Notes on interacting with npm modules / packages via the CLI

## View Versions
```console
npm view {package} versions
```

## View Packages Installed Globally
```console
npm ls --global --depth 0
```

## Inspect Module For Malicious Hooks
```console
npm show $module scripts
```

## Make Package Available Locally
```console
npm link
```

## Use Local Package
```console
npm link package_name
```
