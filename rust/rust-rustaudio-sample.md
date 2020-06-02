# RUSTAUDIO SAMPLE

## Summary
Notes on using the RustAudio Sample crate

## Links
[Github](https://github.com/RustAudio/sample)
[Docs](https://docs.rs/sample/0.10.0/sample/index.html)

## Get Slice Instead Of Vector
```rust
  let f32_samples: Vec<f32> = i24_samples.into_iter().map(I24::to_sample::<f32>).collect();
  let samples = f32_samples.as_slice();
  let frames = sample::slice::to_frame_slice(&samples);
```
or
```rust
  let f32_samples: Vec<f32> = i24_samples.into_iter().map(I24::to_sample::<f32>).collect();
  let frames = sample::slice::to_frame_slice(&f32_samples[..]);
```
