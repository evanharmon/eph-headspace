# GIT FILES

## Summary

Notes on working with files with GIT

## Resources

- [git add docs](https://git-scm.com/docs/git-add)
- [git rm docs](https://git-scm.com/docs/git-rm)

### Adds All New or Changed (as long as not ignored)

but no rm actions

```console
git add .
```

### Remove Files By Glob Pattern

```console
git rm unix-linux\*.md
```

### Look at already Tracked Files and Stage Changes

Including rm Actions

```console
git add -u
```

### shortcut for: git add .;git add -u

```console
git add -A
```

### List Files Being Tracked

```console
git ls-tree -r master --name-only
```

### List Git-ignored Files

```console
git ls-files . --ignored --exclude-standard --others
```

### List Files in Another Branch

```console
git ls-tree -r --name-only develop helpers/
```

### List Untracked Files

```console
git ls-files . --exclude-standard --others
```

### Remove Folder From Being Tracked by Git

```console
git rm --cached -r .config/nvim/plugged/
```

### Remove File Without Deleting

```console
git rm --cached file
```

### List Files Changed in Commit

```console
git show --pretty="format:" --name-only {git commit hash}
```

### View a File From Another Branch

```console
git show branch:filename
```

### Checkout File from Another Branch

```console
git checkout {branch} -- {filepath}
```

### Checkout File From Another Commit

```console
git checkout {commit-hash} file/to/restore
```

### Checkout Entire Folder From Another Branch

\*\*Note: You can't checkout a folder to a new folder path. Has to be done in
separate steps

```console
git checkout backup/non-cra-master -- public/
git mv public/ src/
```

### Remove All Un-tracked Files

```console
git clean -i
```

### View Commit History by Specific File

```console
git log -- /directory/file.js
```

### List unique current directory commit changes

```console
$(git ls-files --directory <directory-name> | sed 's/\(.*\)\/.*/\1/' | uniq)
```

### Correctly Symlink Folders With `bindfs`

- [SO at the bottom](https://stackoverflow.com/questions/86402/how-can-i-get-git-to-follow-symlinks)

On Mac:

```console
brew install bindfs
cd /path/to/git_controlled_dir
mkdir local_copy_dir
bindfs <source_dir> local_copy_dir
```

### List Last Modification of Files In Folder

```console
git ls-tree -r --name-only HEAD ./| while read filename; do
  echo "$(git log -1 --format="%ad" -- $filename) $filename"
done
```

### List all files ever tracked in git

```console
git log --pretty=format: --name-only | cut -f2- | sort -u
```

### Remove file from all git history and force push

```console
git filter-branch --force --index-filter "git rm --cached --ignore-unmatch PATH_TO_FILE" --prune-empty --tag-name-filter cat -- --all
```

### Remove Folder from all git history and force push

```console
git filter-branch --force --index-filter "git rm -r --cached --ignore-unmatch PATH_TO_FOLDER" --prune-empty --tag-name-filter cat -- --all
```
