# RUST LLDB

## Summary

RUST LLDB Compiler / Debugger

## Start The Debugger

```console
rust-lldb target/debug/deps/rusty_power_converter-dd9993aa71fbc8ad
```

## Run The Debugger

```console
r
```

## Breakpoints

Set Breakpoint By Function

```console
b find_spectral_peak
```

## Variables

See current variables

```console
frame variable
```

Print out variable from frame list

```console
p filename
```

View source code

```console
list
```

Step out

```console

```

## Run Test Binary In Debugger

```console
cargo test --no-run
rust-lldb target/debug/myprogram-4f6b5a4156a75d8c
```
