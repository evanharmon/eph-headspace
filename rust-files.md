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

## Open File From Path
```rust
read_and_collect_samples<P: AsRef<Path>>(file_path: P) {}
```

## Open File From String
```rust
fn read_spec_from_file(file_path: &str) -> WavSpec {
    let reader = WavReader::open(file_path).expect("Something went wrong reading the file");
    reader.spec()
}
```
