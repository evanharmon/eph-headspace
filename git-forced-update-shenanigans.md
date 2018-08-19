# GIT FORCE PUSH
Dealing with FORCED UPDATES.

Ex let's say you do a git fetch and dev shows (forced update). Then you get
asked to 'rebase on top of the forced update'. In summary, you create a new
branch from yours, handle the merge/conflicts, then merge that new branch
BACK in to your own. Keeps it safe and able to be undone

## Rebase on top of a forced update dev branch
```
git checkout -b branch-name-post-force-push
git merge dev
```
- resolve conflicts
```
git commit
git checkout branch-name
git merge branch-name-post-force-push
```

keeps history and comments, anything dangerous is handled in a separate branch,
so you can retry if things go wrong
