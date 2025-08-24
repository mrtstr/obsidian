### trait
- in [[rust]] a [[r trait]] is the equivalent to an interface in [[python]] or java
```rust
struct Person {
    name: String,
}

impl Greet for Person {
    fn say_hello(&self) {
        println!("Hello, my name is {}", self.name);
    }
}

fn main() {
    let p = Person { name: "Martin".into() };
    p.say_hello();
}
```