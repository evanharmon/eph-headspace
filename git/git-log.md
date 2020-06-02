# GIT LOG

## Summary

Notes on working with git log

## Resources

## Check Log

```console
git log
```

## Check Log One Line

```console
git log --oneline
```

## Check Log by Author Commiter

```console
git log --author=evan
```

## Check Log of Merges

```console
git log --merges
```

## View last commit message

```console
git log -1
```

## Show Files Changed By Each Commit

```console
git log --stat
```

## Files

### Show Files Changed By Each Commit

```console
git log --stat
```

### See Files Changed In Last 10 Commits

```console
git log -name-status -10 ./
```

## Show Total Contributions For Repo

````console
git log --shortstat --pretty="%cE" | sed 's/\(.*\)@.*/\1/' | grep -v "^$" | awk 'BEGIN { line=""; } !/^ / { if (line=="" || !match(line, $0)) {line = $0 "," line }} /^ / { print line " # " $0; line=""}' | sort | sed -E 's/# //;s/ files? changed,//;s/([0-9]+) ([0-9]+ deletion)/\1 0 insertions\(+\), \2/;s/\(\+\)$/\(\+\), 0 deletions\(-\)/;s/insertions?\(\+\), //;s/ deletions?\(-\)//' | awk 'BEGIN {name=""; files=0; insertions=0; deletions=0;} {if ($1 != name && name != "") { print name ": " files " files changed, " insertions " insertions(+), " deletions " deletions(-), " insertions-deletions " net"; files=0; insertions=0; deletions=0; name=$1; } name=$1; files+=$2; insertions+=$3; deletions+=$4} END {print name ": " files " files changed, " insertions " insertions(+), " deletions " deletions(-), " insertions-deletions " net";}'```
````
