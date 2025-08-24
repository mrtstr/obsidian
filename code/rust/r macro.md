```rust
macro_rules! print_type {
    ($val:expr) => {
        println!("{}: {}", stringify!($val), std::any::type_name::<_>());
    };
}

```