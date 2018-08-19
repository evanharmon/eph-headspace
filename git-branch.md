# GIT BRANCHES

## Set Upstream
`$ git branch -u`

## Show Upstreams
`git branch -vv`

## Checkout Previous Branch
`$ git checkout -`

## Update branch information from origin and clean out stales
`$ git fetch -p`

## Update different branch while on another branch
`$ git fetch origin dev:dev`

## Create local branch
`$ git checkout -b new_feature_name`

## Create local branch from remote branch
`$ git checkout --track origin/lh-shopping-cart`

## Push New Local Branch to Remote
`$ git push -u origin <branchName>`

## Set Remote for Tracking
```
$ git branch -u origin/branchname
$ git remote add origin https://github.com/GetLevvel/siemens.git
$ git push -u origin master
```

## Delete Local Branch
`$ git branch -d branch_name`

## List Branches
-a for local and remote branches
-r for only remote branches
`$ git branch --list`

## Delete a Remote Branch
`$ git push origin --delete <branchName>`

## Resetting Branch, if no unsaved/unpushed commits exist
`$ git reset --hard origin/dev`

## Rename Current Branch
`$ git branch -m <newname>`

## DANGER DANGER Force Push a Branch To Remote
`$ git push --force-with-lease origin <branchname>`
