# RUST REFERENCES

## Summary
Notes on using referencing and de-referencing in Rust


## Borrowing
`as_ref()` returns a reference instead of taking ownership

## Common Mistakes


#### Can't compare &f64 with float
```rust
let predicate = |f: [f64; 2]| f.iter().skip_while(|s| s == 0.0);
```
should be
```rust
let predicate = |f: [f64; 2]| f.iter().skip_while(|&s| *s == 0.0);
```

#### Collection of type `std::vec::Vec<&[f64; 2]>` cannot be built from an
iterator over elements of type `&&[f64; 2]`
Need an extra deference. `.map(...)` is good for this
```rust
frames
    .iter()
    .filter(|&f| f[0] > 0.0 || f[1] > 0.0)
    .collect()
```
should be
```rust
frames
    .iter()
    .filter(|&f| f[0] > 0.0 || f[1] > 0.0)
    .map(|&f| f)
    .collect()
```

#### Pass borrowed reference of a 2d array to a function
```rust
fn find_start(frames: &[[f64; 2]]) -> Option<usize> {
    frames.iter().position(|&f| f[0] > 0.0 || f[1] > 0.0)
}

fn main() {
    let signal = vec![[0.0, 0.0], [0.1, 0.01], [0.013, 0.013]];
    let start_frame = find_start(&signal);

    assert_eq!(start_frame.unwrap(), 1);
    println!("{:?}", start_frame.unwrap());
}
```
