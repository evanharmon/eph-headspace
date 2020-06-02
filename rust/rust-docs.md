# RUST DOCS

## Summary
Notes on using rust docs syntax

## Unresolved Import In Doc Example
[SO](https://stackoverflow.com/questions/31638263/unresolved-import-in-documentation-example)
rust is adding a main like so
```rust
fn main() {
   extern crate bignum;
   use bignum::inits::Zero;

   let a = bignum::BigNum::new(Zero::zero());
}
```
