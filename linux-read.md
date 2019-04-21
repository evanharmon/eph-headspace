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
