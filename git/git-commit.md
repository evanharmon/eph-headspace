# GIT COMMIT

## Reword Last Commit Message

```console
git commit --amend
```

## Reword Commit Message Further Behind

let's say last 4

```console
git rebase -i HEAD~4
```

in editor window, use 'r' for reword

## Change Previous Commit

This will need a force push if the branch is on remote - CAREFUL good if you
forgot a debug/log message in a previous commit

```console
git rebase -i HEAD~2 ## 2 is number of commits to go back
```

In editor, change the 'pick' word to 'e' for the commit you want to edit. Save
and quit file. Make change and then:

```console
git commit --amend
git rebase --continue
```

## Dates

Change Date of Current Commit

```console
git commit --amend --date="Wed Feb 16 14:00 2011 +0100"
```

or for current timestamp \$(date -R) if on linux

```console
git commit --amend --date="$(date)"
```

## Search Commits

```console
git log --grep=/pattern/
git log --oneline | ag PATTERN
```

By Author

```console
git log --oneline --author="Evan Harmon"
```
