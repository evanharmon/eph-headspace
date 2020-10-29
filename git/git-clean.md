# GIT CLEAN

## Summary

Notes on using git clean

## Resources

- [Docs](https://git-scm.com/docs/git-clean)
- [SO](https://stackoverflow.com/questions/61212/how-to-remove-local-untracked-files-from-the-current-git-working-tree)

### Remove Untracked Files

useful after a refactor / adjusting the .gitignore

dry run

```console
git clean -n
```

after careful review, remove the files

```console
git clean -f
```
