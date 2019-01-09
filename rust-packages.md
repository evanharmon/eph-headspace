# RUST PACKAGES

## Summary
Notes on using packages and modules in Rust


## Use Of Unstable Library Feature
External crate needs to be added to Cargo.toml
```rust
#[macro_use]
extern crate log;
```

## Use Module From Different File
[Gist](https://gist.github.com/dumindu/3f53ce161149b66e2251e3dcb742b94a)
```rust
// ↳ main.rs
mod greetings; // import greetings module

fn main() {
  greetings::hello();
}

// ↳ greetings.rs
// ⭐️ no need to wrap the code with a mod declaration. File itself acts as a module.
pub fn hello() { // function has to be public to access from outside
  println!("Hello, world!");
}
```

## Wrap Module With Mod
[Gist](https://gist.github.com/dumindu/1515be04ba8fb8ed39191b354c7e7e9b)
```rust
// ↳ main.rs
mod phrases;

fn main() {
  phrases::greetings::hello();
}

// ↳ phrases.rs
pub mod greetings { // ⭐️ module has to be public to access from outside
  pub fn hello() {
    println!("Hello, world!");
  }
}
```
## Use Module From Different Directory
[Gist](https://gist.github.com/dumindu/03ed2c9c8df1c7734938c751cb6b99a5)
```rust
// ↳ main.rs
mod phrases;

fn main() {
    phrases::hello(); //not directly map
}

// ↳ phrases/mod.rs
pub mod greetings;

pub use self::greetings::hello; //re-export greetings::hello to phrases

// ↳ phrases/greetings.rs
pub fn hello() {
  println!("Hello, world!");
}
```
