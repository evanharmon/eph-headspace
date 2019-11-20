# GIT STASH

## Summary

Notes on using git stash

## Resources

## Save a Stash

`$ git stash save "WIP-time-functions"`

## Apply Stash by Number

use quotes to escape curly brackets
`$ git stash apply stash@'{'1'}'`

## Apply Stash by Name

`$ git stash apply stash^{;/time\-functions}`

## Drop A Stash by Number

`$ git stash drop stash@'{'2’}'`

## View Files in Stash

`$ git stash show -p stash@‘{‘2’}’`

## View Diff of File in Stash

`$ git diff HEAD stash@‘{‘2’}’ — src/index.js`

## Check Stash Age Timestamp

```console
git stash list --date=relative
```
