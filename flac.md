# FLAC

## Summary

Notes on working with FLAC files

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
