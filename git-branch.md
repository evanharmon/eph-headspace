# GIT BRANCHES

## Set Upstream

```console
git branch -u
```

## Show Upstreams

```console
git branch -vv
```

## Checkout Previous Branch

```console
git checkout -
```

## Update branch information from origin and clean out stales

```console
git fetch -p
```

## Update different branch while on another branch

```console
git fetch origin dev:dev
```

## Create local branch

```console
git checkout -b new_feature_name
```

## Create local branch from remote branch

```console
git checkout --track origin/lh-shopping-cart
```

## Push New Local Branch to Remote

```console
git push -u origin <branchName>
```

## Push And Set Upstream

```console
git branch --set-upstream-to origin feature-branch
```

## Delete Local Branch

```console
git branch -d branch_name
```

## List Branches

-a for local and remote branches
-r for only remote branches

```console
git branch --list
```

## Delete a Remote Branch

```console
git push origin --delete <branchName>
```

## Resetting Branch, if no unsaved/unpushed commits exist

```console
git reset --hard origin/dev
```

## Rename Current Branch

```console
git branch -m <newname>
```

## DANGER DANGER Force Push a Branch To Remote

```console
git push --force-with-lease origin <branchname>
```
