# RUST FILES

## Summary

Notes on interacting with Files in rust

## Links

[Docs](https://rust-lang-nursery.github.io/rust-cookbook/file/read-write.html)

## Read Entire File In To String

```rust
let mut file = File::open("foo.txt")?;
let mut contents = String::new();
file.read_to_string(&mut contents)?;
assert_eq!(contents, "Hello, world!");
```

## Read Entire File In To Bytes

```rust
let mut f = File::open("foo.txt")?;
let mut buffer = Vec::new();
f.read_to_end(&mut buffer)?;
```

## Read Exact Number Of Bytes

```rust
use std::io::prelude::*;

let mut f = File::open("foo.txt")?;
let mut buffer = [0; 10];
f.read_exact(&mut buffer)?;
```

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
