# Search for String in Files in Directory

`$ grep -r "user" ./lib`

# Search string in File show only filename

`$ grep -rl "uib-typeahead" ./app`

# Search for Filename in Directory

`$ use find not grep`

# Show Line Numbers

`$ grep -n`

# Search for String but Exclude a Directory

`$ grep -R --exclude-dir=node_modules 'some pattern' /path/to/search`

## Find Matching Strings Between Files

example format of txt files

```txt
1234,
1235
```

```console
grep -f file1.txt file2.txt | tee matches.txt
```
