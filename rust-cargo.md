# RUST CARGO

## Start A New Project With Binary
[Guide](http://doc.crates.io/guide.html)
Creates a .git folder as well
```console
cargo new hello_world --bin
```

## Start A New Project As Library
[Guide](http://doc.crates.io/guide.html)
Creates a .git folder as well
```console
cargo new hello_world --lib
```

## Start Project With No .git Folder
```console
cargo new mybin --bin --vcs none
cargo new mylib --lib --vcs none
```

## Add A Package To Cargo.toml
```console
rustfmt = "0.9.0"
```

## Install Dependencies
```console
cargo build
```
