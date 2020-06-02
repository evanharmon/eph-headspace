# GIT DIFF

## Summary

Notes on using the git diff tool

## Resources

- [Git Diff Docs](https://git-scm.com/docs/git-diff)

## Diff of a File Between Branches

```console
git diff branch1 branch2 -- {file}
```

## Show Files Changed Between Branches

```console
git diff firstbranch..secondbranch
```

only show filenames

```console
git diff --name-status firstbranch..secondbranch
```
