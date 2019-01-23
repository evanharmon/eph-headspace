# RUST SLICES

## Summary
Notes on using slices in rust

## What Is A Slice?
[SO](https://stackoverflow.com/questions/30794235/what-is-the-difference-between-a-slice-and-an-array)
A Slice is an indirection [T]. `starts_with` excepts a slice
[Docs.rs for starts_with](https://docs.rs/predicates/1.0.0/predicates/str/fn.starts_with.html)
```rust
[1, 2, 3].starts_with(&[1, 2]);
```

## Get A Slice Of A Slice
[Reddit](https://www.reddit.com/r/rust/comments/5cvok8/copying_parts_of_slice/)
```rust
let a: [i32; 10] = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
let b = (&a[..4]).clone();
println!("{:?}, {:?}", a, b);
```

## Copy The Contents Of A Slice With Ownership
[SO](https://stackoverflow.com/questions/35664419/how-do-i-duplicate-a-u8-slice)
Have to use a Vector

```rust
/// custom function
fn clone_into_array<A, T>(slice: &[T]) -> A
where
    A: Default + AsMut<[T]>,
    T: Clone,
{
    let mut a = Default::default();
    <A as AsMut<[T]>>::as_mut(&mut a).clone_from_slice(slice);
    a
}

// WAV Header containing
// ["RIFF", "4_160_292" ,"WAVE"]
let header = [82, 73, 70, 70, 36, 123, 63, 0, 87, 65, 86, 69];
// get bytes 4 thru 8 as an array
let slice: &[u8] = (&header[4..8]).clone();
let chunk: [u8;4] = clone_into_array(&slice);
let chunk_size = read_chunk_size(chunk);
// compare chunk_size
let file_size_bytes = 4_160_300;
assert_eq!(chunk_size, file_size_bytes - 8 as u32);
```
