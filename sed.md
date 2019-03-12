# SED

## Summary

Notes on using SED

## Search and Replace

```console
sed -i .bak 's/hello/bonjour/' file.txt
```

## Search And Replace In A File From Shell Command

```console
sed -i 's/REPLACE_WITH_INSTANCE_IP/'$INSTANCE_IP'/g' /tmp/init-cluster.sh
```

## Print First 10 Lines Of File

Emulates `head`

```console
sed 10q
```

## Print First Line Of File

Emulates `head -1`

```console
sed q
```

## Find And Replace On Mac OS X

avoids the `invalid command code` error

```console
find ./**/*.tf -type f -exec sed -i '' -e "s/\? false/\? \"false\"/g" {} \;
```
