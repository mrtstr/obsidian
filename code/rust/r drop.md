### drop
- in [[rust]] the deconstructor is defined by implementing the [[r drop]] [[r trait]]
- drop is almost never explicitly called, but it is called automatically when the pointer leaves the [[li stack]] because the [[r scope]] is over 

```rust
struct Resource;

impl Drop for Resource {
    fn drop(&mut self) {
        println!("Resource is being dropped!");
    }
}

fn main() {
    let r = Resource;
    println!("Created resource");
} // <-- `r.drop()` is called automatically here
```

- [[r drop]] is not implemented [[rust]] is generating a default drop function

```rust
struct Foo {
    name: String,
    nums: Vec<i32>,
}

fn main() {
    let f = Foo {
        name: String::from("Hello"),
        nums: vec![1, 2, 3],
    };
} // <- Rust automatically drops f.nums, then f.name, then f
```