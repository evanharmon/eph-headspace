# GIT FILES

## Adds All New or Changed (as long as not ignored)

but no rm actions

```console
git add .
```

## Remove Files By Glob Pattern

```console
git rm unix-linux\*.md
```

## Look at already Tracked Files and Stage Changes

Including rm Actions

```console
git add -u
```

## shortcut for: git add .;git add -u

```console
git add -A
```

## List Files Being Tracked

```console
git ls-tree -r master --name-only
```

## List Git-ignored Files

```console
git ls-files . --ignored --exclude-standard --others
```

## List Files in Another Branch

```console
git ls-tree -r --name-only develop helpers/
```

## List Untracked Files

```console
git ls-files . --exclude-standard --others
```

## Remove Folder From Being Tracked by Git

```console
git rm --cached -r .config/nvim/plugged/
```

## Remove File Without Deleting

```console
git rm --cached file
```

## List Files Changed in Commit

```console
git show --pretty="format:" --name-only {git commit hash}
```

## Diff of a File Between Branches

```console
git diff branch1 branch2 -- {file}
```

## View a File From Another Branch

```console
git show branch:filename
```

## Checkout File from Another Branch

```console
git checkout {branch} -- {filepath}
```

## Checkout File From Another Commit

```console
git checkout {commit-hash} file/to/restore
```

## Remove All Un-tracked Files

```console
git clean -i
```

## View Commit History by Specific File

```console
git log -- /directory/file.js
```

## List unique current directory commit changes

```console
$(git ls-files --directory <directory-name> | sed 's/\(.*\)\/.*/\1/' | uniq)
```

## Show Filenames Changed Between Branches

```console
git diff --name-status firstbranch..secondbranch
```
