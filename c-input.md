# C INPUT

## NEVER use gets()
```
char buf[50];
fgets(buf, sizeof buf, stdin);
sscanf(buf, "%d," %n);
```
