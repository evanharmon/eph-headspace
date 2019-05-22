# FLAC

## Summary

Notes on working with FLAC files

## Install

amazon-linux `yum install -y libogg-devel flaclib-devel`

## Header

[Format](https://xiph.org/flac/format.html#frame_header)

#### Read Header Info From File With Metaflac

```console
metaflac --list my-file.flac
```

#### Read Header From File As Hex

```console
hexdump my-file.flac| head -n 6
```

#### Read Header In Python

```python
with open("myfile.flac", "rb") as binary_data:
    # metadata block is first 32 bytes
    data = binary_data.read(32)
    metadata = binascii.hexlify(data)
    print(metadata)
    numsamples = data[8:16]
    print("numsamples ",numsamples)
```
