# RUST READ

## Summary

Notes on reading from Files / Buffers / Streams in rust

### Read Specific Number of Bytes In To A Buffer

```rust
    use std::io::Read;
    let mut f = std::fs::File::open("tests/data/test-kit-sampling.wav").unwrap();
    let mut buffer = [0u8;4];
    f.read(&mut buffer).unwrap();
```
