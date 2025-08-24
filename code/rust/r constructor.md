### constructor
- in [[rust]] there is no out of the box [[r constructor]] concept, but can be implemented using a [[r associated function]] the following patter
- by convention this function is named `new`
```rust
struct User {
    username: String,
    age: u32,
}

impl User {
    // Constructor pattern
    fn new(username: String, age: u32) -> Self {
        Self { username, age }
    }
}

fn main() {
    let u = User::new("martin".to_string(), 30);
    println!("{} is {} years old", u.username, u.age);
}
```


# anki

START
Basic
- constructor and deconstructor in [[rust]] with example

Back: 
### constructor
- in [[rust]] there is no out of the box [[r constructor]] concept, but can be implemented using a [[r associated function]] the following patter
- by convention this function is named `new`
```rust
struct User {
    username: String,
    age: u32,
}

impl User {
    // Constructor pattern
    fn new(username: String, age: u32) -> Self {
        Self { username, age }
    }
}

fn main() {
    let u = User::new("martin".to_string(), 30);
    println!("{} is {} years old", u.username, u.age);
}
```

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


________________

### associated function
- in [[rust]] is the equivalent to a `static function/class function` in [[python]] 
- function that is associated with the [[r struct]] itself and not with one instance
- every [[r function]] of a [[r struct]] that does not have a self [[r pointer#reference]] is a [[r associated function]] and can only be called with `MyStructType::my_associated_function(...)`

```rust
struct Rectangle { width: u32, height: u32 }
impl Rectangle {
	// Associated function (often used as a "constructor")
	fn my_associated_function(width: u32, height: u32) -> u32 {
	width*height
}

fn area(&self) -> u32 {
	self.width * self.height
	}
}

fn main() {
	let r = Rectangle{ width: 10, height: 20 }; // Type::function — associated fn
	println!("{}", Rectangle::my_associated_function(r.width, r.height)); // associated fn
	println!("{}", r.area()); // r.method() — instance method
}
main();
```

Tags: code rust
<!--ID: 1756052658841-->
END