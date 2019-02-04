# RUST WAVS

## Summary
Notes on readiung and writing WAV files in Rust with NO external libraries

## Read WAV Header And Pass Slices As Arrays
```rust
use std::io::prelude::*;

let mut f = std::fs::File::open("tests/data/test-kit-sampling.wav").unwrap();
let mut buf = [0;44];
f.read_exact(&mut buf).unwrap();
let slice = (&buf[40..44]).clone();
let arr = clone_into_array(&slice);
```
