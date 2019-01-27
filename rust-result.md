# RUST RESULT

## Summary
Notes on rust error handling

[Rust By Example](https://doc.rust-lang.org/rust-by-example/std/result.html)
result expresses the possibility of error

## unused `std::result::Result`
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
