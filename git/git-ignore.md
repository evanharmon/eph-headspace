# GIT IGNORE

## Filename
.gitignore

## Ignore Folder
./node_modules

## Exclude all but whitelisted files/folders
Ignore everything
`*`

But include these files...
```
!.gitignore
!script.pl
!template.latex
```

...even if they are in subdirectories
`!*/`
