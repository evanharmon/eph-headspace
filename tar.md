# TAR

## Summary

Notes on using the tar cli

## Resources

## Tar As Root To /

```console
sudo tar -xzvf greengrass-OS-architecture-1.10.0.tar.gz -C /
```

## Append File to Archive

--append
-r

## Extract Tar To Another Directory

```console
tar -xf archive.tar -C $HOME/.cache
```

## Use File Archive as Tar Archive

--file=archive
-f archive

## Read or Write via gzip

--gzip
--gunzip
--ungzip
-z

## Extract tar.gz

```console
tar -xzf
```

## Extract tar.bz2

```console
tar -xjf
```

## Create Tar file zipped

```console
tar zcvf file.tar file1.txt file2.txt
```
