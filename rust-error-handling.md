# RUST ERROR HANDLING

## Summary
Notes on rust error handling

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
