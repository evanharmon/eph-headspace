# GIT FILES

## Adds All New or Changed (as long as not ignored)
but no rm actions
`$ git add .`

## Look at already Tracked Files and Stage Changes
Including rm Actions
`$ git add -u`

## shortcut for: git add .;git add -u
`$ git add -A`

## List Files Being Tracked
`$ git ls-tree -r master --name-only`

## List Git-ignored Files
`$ git ls-files . --ignored --exclude-standard --others`

## List Files in Another Branch
`$ git ls-tree -r --name-only develop helpers/`

## List Untracked Files
`$ git ls-files . --exclude-standard --others`

## Remove Folder From Being Tracked by Git
`$ git rm --cached -r .config/nvim/plugged/`

## Remove File Without Deleting
`$ git rm --cached file`

## List Files Changed in Commit
`$ git show --pretty="format:" --name-only {git commit hash}`

## Diff of a File Between Branches
`$ git diff branch1 branch2 -- {file}`

## View a File From Another Branch
`$ git show branch:filename`

## Checkout File from Another Branch
`$ git checkout {branch} -- {filepath}`

## Checkout File From Another Commit
`$ git checkout {commit-hash} file/to/restore`

## Remove All Un-tracked Files
`$ git clean -i`

## View Commit History by Specific File
`$ git log -- /directory/file.js`
