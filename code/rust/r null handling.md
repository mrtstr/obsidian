```rust
enum Option<T> { Some(T), None }

let x = Some(5);

match x {
    Some(v) => println!("value = {v}"),
    None => println!("no value"),
}
```