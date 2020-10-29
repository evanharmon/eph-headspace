# Find Command

## Summary

Notes on using the find command

## Resources

- [Tutorial](https://www.digitalocean.com/community/tutorials/how-to-use-find-and-locate-to-search-for-files-on-a-linux-vps)

## Search for filename recursively

### . means current directory, asterix is important bc it's not regex partial match like grep

```console
find . -name "login*"
```

## Find by date time by Days

### Access Time -atime

### Modification Time -mtime

Change Time -ctime

```console
find ./ -mtime 1
```

Less than a day

```console
find ./ -ctime -1
```

Find by date time by Minutes

```console
find ./ -mmin -1
```

## List # of folders in a sub-folder

```console
find ./folder-name -mindepth 1 -maxdepth 1 -type d | wc -l
```

## Find files above size

```console
find /usr -size +1M
```

## Exec To Remove

use specific folder name and max depth for safety / speed

### Remove Directories With Exec

dry run

```console
find ./folder-name -maxdepth 1 -type d -name ".terraform" -print
```

delete

```console
find ./folder-name -maxdepth 1 -type d -name ".terraform" -prune -exec rm -rf {} \;
```

### Remove Files With Exec

dry run

```console
find ./folder-name -maxdepth 1 -type f -name ".env" -prune -exec rm -rf {} \;
```

delete

```console
find ./folder-name -maxdepth 1 -type f -name ".env" -prune -exec rm -rf {} \;
```
