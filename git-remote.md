# GIT REMOTE

## Summary
Notes on setting git remotes

## Set Remote for Tracking
```
$ git branch -u origin/branchname
$ git remote add origin https://github.com/evanharmon/my-repo.git
$ git push -u origin master
```

## Add Additional Mirror To Remote
example: aws codecommit as additional mirror, git push will push to both repos now
```console
git remote set-url --add origin ssh://git-codecommit.us-east-1.amazonaws.com/v1/repos/my-repo
```
