# RUST RESULT

## Summary
Notes on custom error types in rust
[Medium](https://medium.com/@fredrikanderzon/custom-error-types-in-rust-and-the-operator-b499d0fb2925)
Rust custom error types must implement the following: Debug, Display, Error
[Article](https://stevedonovan.github.io/rust-gentle-intro/6-error-handling.html)

## Custom Type
```
#[derive(Debug)]
pub enum FilerError {
    InvalidHeader,
}
```

## fmt::Display Required Implementation
```rust
impl fmt::Display for FilerError {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        match *self {
            FilerError::InvalidHeader => f.write_str("Invalid WAV Header"),
        }
    }
}
```

## Required Error Description Implementation
```rust
impl std::error::Error for FilerError {
    fn description(&self) -> &str {
        match *self {
            FilerError::InvalidHeader => "Invalid WAV Header"
        }
    }
}
```

## Example Use
```rust
fn clone_into_array<A, T>(slice: &[T]) -> A
where
    A: Default + AsMut<[T]>,
    T: Clone,
{
    let mut a = Default::default();
    <A as AsMut<[T]>>::as_mut(&mut a).clone_from_slice(slice);
    a
}

fn read_and_verify_chunk_id(buffer: [u8;4]) -> Option<()> {
    if buffer == [82, 73, 70, 70] {
        Some(())
    } else {
        None
    }
}

pub fn read_chunk_size(b: [u8;4]) -> u32 {
    u32::from_le_bytes(b)
}

pub fn read_and_verify_format(buffer: [u8;4]) -> Option<()> {
    if buffer == [87, 65, 86, 69] {
        Some(())
    } else {
        None
    }
}

fn read_header_chunk_size(buf: [u8;12]) -> Result<u32, FilerError> {
    // verify RIFF
    let id_clone = clone_into_array((&buf[1..4]).clone());
    match read_and_verify_chunk_id(id_clone) {
        Some(()) => (),
        None => return Result::Err(FilerError::InvalidHeader),
    }

    // verify WAVE
    let wave_clone = clone_into_array((&buf[8..12]).clone());
    read_and_verify_format(wave_clone).unwrap();

    // get chunk size
    let chunk_clone = clone_into_array((&buf[4..8]).clone());
    let chunk_size = read_chunk_size(chunk_clone);

    Ok(chunk_size)
}
```
