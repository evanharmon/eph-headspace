# GIT MERGE

## Merge Branch to Check Conflicts
dry runs are done with --no-commit
THEN UNDO
```
$ git merge --no-commit --no-ff development
$ git merge --abort
```

## Find the Common Ancestor
`$ git merge-base branch2 branch3`
