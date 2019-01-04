# RUST ARRAYS

## Summary
Notes on Rust arrays, vectors, slices

## Arrays VS Slices
[SO](https://stackoverflow.com/questions/27554838/what-is-the-difference-between-vecstruct-and-struct)

## Common Mistakes

#### mismatched types expected &[[f64; 2]], found struct `std::vec::Vec`
A slice must be passed NOT a vector
```rust
let frames: Vec<[f64; 2]> = signal.map(|f| f).collect();
let trimmed_samples = find_start(frames.as_slice());
```

## Iterate Over Slice Of Vector
[SO](https://stackoverflow.com/questions/40613725/iterating-over-a-slices-values-instead-of-references-in-rust/40613870)
```rust
fn main() {
    let v = vec![1, 2, 3];
    let slice = &v[..];
    for u in slice.iter().cloned() {
        let u: usize = u; // prove it's really usize, not &usize
        println!("{}", u);
    }
}
```
