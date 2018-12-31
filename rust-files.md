# RUST FILES

## Summary
Notes on interacting with Files in rust

## Links
[Docs](https://rust-lang-nursery.github.io/rust-cookbook/file/read-write.html)

## Write To File As One Line
```rust
let strings: String = frames.clone().map(|f| format!("{:?}", f)).collect();
let mut file = File::create("log.txt").expect("create file");
write!(file, "{}", strings).expect("write to file");
```

## Write Line To File 
```rust
```
