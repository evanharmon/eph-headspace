# C STRINGS

## Convert Memory Location To String
```
int n = 1;
char *address = (char *)&n
```

## Copy String Off Stack To Return In A Function
```
char str[512];
str = "This is a sentence.";
return strdup(str);
```

## Atoi
converts string argument to integer
```
char str[20];
strcpy(str, "98993489");
int i = atoi(str);
```

## Strtok
modifies original string - so copy first

## Compare Strings
```
char str1[15];
char str2[15];
int ret;

strcpy(str1, "abcdef");
strcpy(str2, "ABCDEF");

ret = strncmp(str1, str2, 4);
```
