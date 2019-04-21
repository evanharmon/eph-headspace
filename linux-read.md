# LINUX READ

## Summary

Notes on using the linux `read` command

## Read File Line By Line

[Guide](https://www.cyberciti.biz/faq/unix-howto-read-line-by-line-from-file/)

```bash
#!/bin/bash
input="tdm.builders.kicks.txt"
while IFS= read -r var
do
  echo "$var"
done < "$input"
```

## Read File By Field And Line

[Guide](https://www.cyberciti.biz/faq/unix-howto-read-line-by-line-from-file/)

```bash
#!/bin/bash
file="/etc/passwd"
while IFS=: read -r f1 f2 f3 f4 f5 f6 f7
do
        # display fields using f1, f2,..,f7
        printf 'Username: %s, Shell: %s, Home Dir: %s\n' "$f1" "$f7" "$f6"
done < "$file"
```
