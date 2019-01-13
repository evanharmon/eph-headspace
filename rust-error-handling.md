# RUST ERROR HANDLING

## Summary
Notes on rust error handling


## Option
[Rust By Example](https://doc.rust-lang.org/rust-by-example/std/option.html)
option expresses the possibility of absence

#### unused `std::option`
[docs.rs](https://doc.rust-lang.org/1.5.0/book/error-handling.html#the-option-type)
[medium](https://medium.com/adventures-in-rust/deal-with-it-option-type-in-rust-4246e1dd9e47)
example function:
```rust
fn find_index(names: &[String], element: String) -> Option<usize> {
  for (i, name) in names.iter().enumerate() {
    if name == element {
      return Some(i);  
    }
  }
  return None;
}
```

handle Option:
```rust
match find_index(names, element) {
    Some(i) => println!("Name is at {}", i),
    None    => println!("Name is not found"),
}
```

handle Option idiomatically:
```rust
find_index(names, name_not_in_names).unwrap();
```
or
```rust
find_index(names, name_not_in_names).unwrap_or(0);
```

## Result
[Rust By Example](https://doc.rust-lang.org/rust-by-example/std/result.html)
result expresses the possibility of error

#### unused `std::result::Result`
code with warning
```rust
for _frame in frames.clone() {
    writeln!(file, "{:?}", _frame);
}
```

need to use an expect()
```rust
for _frame in frames.clone() {
    writeln!(file, "{:?}", _frame).expect("write line to file");
}
```
