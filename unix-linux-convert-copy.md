# UNIX LINUX CONVERT COPY

## Summary

Notes on converting and copying files in NIX variants

## DD

if is input, of is output

```console
sudo dd if=/dev/sda of=bootloader.bak bs=446 count=1
```

# View File As Hex

```console
xxd bootloader.bak
```

or pipe to `head`

```console
hexdump ../test/keys-stem.flac| head -n 32
```

# View File As Octal

```console
od file.txt
```
