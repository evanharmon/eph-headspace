# RUST ITERATOR

## Summary
Notes on using the rust Iterator

## [Filter](https://doc.rust-lang.org/std/iter/trait.Iterator.html#method.filter)
remember to destructure as needed
```rust
fn zero_crossing_locations(frames: Vec<f64>) -> Vec<f64> {
    frames.into_iter().filter(|&f| f > 0.0).collect()
}
```

```rust
let a = [0, 1, 2];
let mut iter = a.into_iter().filter(|&x| *x > 1); // both & and *
```

```rust
let a = [0, 1, 2];
let mut iter = a.into_iter().filter(|&&x| x > 1); // two &s
```
