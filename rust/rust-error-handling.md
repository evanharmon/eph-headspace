# RUST ERROR HANDLING

## Summary
Notes on rust error handling

## Error

#### Create New Error
```rust
fn get_result() -> Result<String, std::io::Error> {
    Err(std::io::Error::new(std::io::ErrorKind::Other, "foo"))
}
```

#### Cannot Index Into A Value Of Type `std::result::Result<std::vec::Vec<u8>, std::io::Error>`
need to use `?`
```rust
if b"WAVE" != &reader.read_bytes(4)?[..] {
    return Err(Error::FormatError("no WAVE tag found"))?;
}
```

#### Match Arms Have Incompatible Types
Each arm of a match have to return the same kind of type. If returning an error consider this
style.
```rust
pub fn read_header_chunk_size(buf: [u8;12]) -> Result<u32, String> {
    // verify RIFF
    let id_clone = clone_into_array((&buf[1..4]).clone());
    match read_and_verify_chunk_id(id_clone) {
        Some(()) => (),
        None => return Result::Err("Invalid Header".to_string()),
    }
}
```
