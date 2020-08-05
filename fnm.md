# FNM

## Summary

Node version manager

## Resources

- [Github](https://github.com/Schniz/fnm)

## Install Without Touching Shell

```console
curl -fsSL https://github.com/Schniz/fnm/raw/master/.ci/install.sh |\
  bash -s -- --install-dir "./.fnm" --skip-shell --force-install
```

## Upgrade

use `--skip-shell` to avoid duplication in shell scripts

```console
curl -fsSL https://github.com/Schniz/fnm/raw/master/.ci/install.sh |\
  bash -s -- --install-dir "./.fnm" --skip-shell --force-install
```

## Uninstall

- [GH](https://github.com/Schniz/fnm/issues/96)

no uninstall command exists

```console
rm -rf ~/.fnm/node-versions/<VERSION>
```

## Install Node
```console
fnm install v13
```
