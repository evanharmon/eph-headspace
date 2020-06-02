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

## Show Git File Changes During Rebase Edit

```console
git show --name-only
```

## Reset Single File During Rebase Edit

```console
git reset HEAD^ -- .gitignore
```
## Return ALL Edited Files For More Changes During Rebase

```console
git reset HEAD^
```
