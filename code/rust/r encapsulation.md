### encapsulation
- in [[rust]] everything is private per default but can be made public with `pub`
- privacy is based on modules: even if something is private it's still accessible from inside the same module where the [[r struct]] is declared

- this works because `Rectangle` was declared in the root and thus the private [[r field]] `width` can be accessed from inside the main

```rust
struct Rectangle { width: u32, height: u32 }

impl Rectangle {
    fn my_associated_function(width: u32, height: u32) -> u32 {
        width * height
    }

    fn area(&self) -> u32 {
        self.width * self.height
    }
}

fn main() {
    let r = Rectangle { width: 10, height: 20 };
    println!("{}", Rectangle::my_associated_function(r.width, r.height));
}
```

- this does not work because `Rectangle` was declared in a different module

```rust
mod shapes {
    pub struct Rectangle {
        width: u32,   // still private
        height: u32,  // still private
    }

    impl Rectangle {
        pub fn new(w: u32, h: u32) -> Self {
            Self { width: w, height: h }
        }

        pub fn area(&self) -> u32 {
            self.width * self.height
        }
    }
}

fn main() {
    let r = shapes::Rectangle::new(10, 20);

    println!("{}", r.area());       // ✅ works
    // println!("{}", r.width);     // ❌ ERROR: field `width` of struct `shapes::Rectangle` is private
}
```


# anki

START
Basic
- explain the concept of public and private variables in [[rust]]
- does the following snippet work?

```rust
struct Rectangle { width: u32, height: u32 }

impl Rectangle {
    fn my_associated_function(width: u32, height: u32) -> u32 {
        width * height
    }

    fn area(&self) -> u32 {
        self.width * self.height
    }
}

fn main() {
    let r = Rectangle { width: 10, height: 20 };
    println!("{}", Rectangle::my_associated_function(r.width, r.height));
}
```
Back: 
### encapsulation
- in [[rust]] everything is private per default but can be made public with `pub`
- privacy is based on modules: even if something is private it's still accessible from inside the same module where the [[r struct]] is declared

- this works because `Rectangle` was declared in the root and thus the private [[r field]] `width` can be accessed from inside the main

```rust
struct Rectangle { width: u32, height: u32 }

impl Rectangle {
    fn my_associated_function(width: u32, height: u32) -> u32 {
        width * height
    }

    fn area(&self) -> u32 {
        self.width * self.height
    }
}

fn main() {
    let r = Rectangle { width: 10, height: 20 };
    println!("{}", Rectangle::my_associated_function(r.width, r.height));
}
```

- this does not work because `Rectangle` was declared in a different module

```rust
mod shapes {
    pub struct Rectangle {
        width: u32,   // still private
        height: u32,  // still private
    }

    impl Rectangle {
        pub fn new(w: u32, h: u32) -> Self {
            Self { width: w, height: h }
        }

        pub fn area(&self) -> u32 {
            self.width * self.height
        }
    }
}

fn main() {
    let r = shapes::Rectangle::new(10, 20);

    println!("{}", r.area());       // ✅ works
    // println!("{}", r.width);     // ❌ ERROR: field `width` of struct `shapes::Rectangle` is private
}
```
Tags: code rust
<!--ID: 1756052658834-->
END





