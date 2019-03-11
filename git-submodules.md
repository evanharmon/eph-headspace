# GIT SUBMODULES

## Summary

Notes on working with git submodules

## Add Submodule To Repo

```console
git submodule add -b master -- https://git@github.com/myorg/myrepo.git
```

## List Submodules

```console
git config --local --list
```

## Remove Submodule

```console
git config --local --unset submodule.myfolder/mysubsfolder/submodulename.active
git config --local --unset submodule.myfolder/mysubsfolder/submodulename.url
```
