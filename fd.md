# FD

## Summary

Notes on using the fd cli tool

## Resources

- [Github](https://github.com/sharkdp/fd)

## Search Hidden And Ignored Files

```console
fd -HI
```

## Search File Extension

```console
fd -e wav
```

## Show Absolute Path

```console
fd -a Orig.wav
```

## Copy Files To Another Directory

```console
fd -0 -HIa Orig.wav | xargs -0 -I{} cp {} /tmp
```

## Find Files Not Matching

```console
fd -HIa --exclude "*Tape.wav"
```
