# RUST OPTION

## Summary

Notes on rust error handling

## Resources

- [Rust By Example](https://doc.rust-lang.org/rust-by-example/std/option.html)
- [docs.rs](https://doc.rust-lang.org/1.5.0/book/error-handling.html#the-option-type)
- [medium](https://medium.com/adventures-in-rust/deal-with-it-option-type-in-rust-4246e1dd9e47)

### Using an `std::option`

option expresses the possibility of absence

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

### Idiomatic Option Handler

```rust
find_index(names, name_not_in_names).unwrap();
```

or

```rust
find_index(names, name_not_in_names).unwrap_or(0);
```

### Unwrap or else

[Link](https://blog.burntsushi.net/rust-error-handling/)

```rust
fn main() {
    let args: Args = Docopt::new(USAGE)
                            .and_then(|d| d.decode())
                            .unwrap_or_else(|err| err.exit());

    for pop in search(&args.arg_data_path, &args.arg_city) {
        println!("{}, {}: {:?}", pop.city, pop.country, pop.count);
    }
}
```

### Ignore `Some` Value

```rust
match x {
  Some(_) => {},
  None => None
}
```

### Ignore `None` Value

```rust
match x {
  Some(y) => { *y },
  None => {}
}
```
