# GIT REBASE

## Rebase Old Feature Branch on Top of Current Development

```
$ git checkout feature_branch
$ git rebase development
```

## Resetting Branch, If Commits Exist that Need to Be Kept

`$ git rebase -i origin/dev`

## Rebase Overriding Conflicts With Current Branch

```console
git branch
```

outputs something like `feature/sqs`

Very confusing, but this will override master conflicts using code from current
feature branch

```console
git rebase -Xtheirs master
```
