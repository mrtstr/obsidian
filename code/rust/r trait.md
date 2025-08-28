### trait
- in [[rust]] a [[r trait]] is the equivalent to an interface in [[python]] or java
- defines a set of methods (and sometimes constants or types) that a type must implement to "satisfy" that trait.

```rust
struct Person {
    name: String,
}

trait Greet {
    fn say_hello(&self);   // required method (no default)
    
	fn say_goodbye(&self) {  // traits can have default methods
        println!("Goodbye!");
    }
}

impl Greet for Person {
    fn say_hello(&self) {
        println!("Hello, my name is {}", self.name);
    }
}

fn main() {
    let p = Person { name: "Bob".into() };
    p.say_hello();
    p.say_goodbye();
}
```

#### operator interactions
- [[r trait]] implement how [[r struct]] interact with operators like in the following example

```rust
use std::ops::Add;

#[derive(Debug, Clone, Copy)]
struct Rect { width: u32, height: u32 }

impl Add for Rect {
    type Output = Rect;

    fn add(self, rhs: Rect) -> Rect {
        Rect {
            width:  self.width  + rhs.width,
            height: self.height + rhs.height,
        }
    }
}

fn main() {
    let a = Rect { width: 3, height: 4 };
    let b = Rect { width: 5, height: 6 };
    let c = a + b; // moves a and b
    println!("{:?}", c);
}
```
# anki

START
Basic
[[r trait]] in [[rust]]
- concept
- how to define it
Back: 
### trait
- in [[rust]] a [[r trait]] is the equivalent to an interface in [[python]] or java
- defines a set of methods (and sometimes constants or types) that a type must implement to "satisfy" that trait.

```rust
struct Person {
    name: String,
}

trait Greet {
    fn say_hello(&self);   // required method (no default)
    
	fn say_goodbye(&self) {  // traits can have default methods
        println!("Goodbye!");
    }
}

impl Greet for Person {
    fn say_hello(&self) {
        println!("Hello, my name is {}", self.name);
    }
}

fn main() {
    let p = Person { name: "Bob".into() };
    p.say_hello();
    p.say_goodbye();
}
```

#### operator interactions
- [[r trait]] implement how [[r struct]] interact with operators like in the following example

```rust
use std::ops::Add;

#[derive(Debug, Clone, Copy)]
struct Rect { width: u32, height: u32 }

impl Add for Rect {
    type Output = Rect;

    fn add(self, rhs: Rect) -> Rect {
        Rect {
            width:  self.width  + rhs.width,
            height: self.height + rhs.height,
        }
    }
}

fn main() {
    let a = Rect { width: 3, height: 4 };
    let b = Rect { width: 5, height: 6 };
    let c = a + b; // moves a and b
    println!("{:?}", c);
}
```

Tags: code rust
<!--ID: 1756383003738-->
END


START
Basic
how to create a [[r struct]] that is addable in [[rust]]
Back: 
### trait
- in [[rust]] a [[r trait]] is the equivalent to an interface in [[python]] or java
- defines a set of methods (and sometimes constants or types) that a type must implement to "satisfy" that trait.

```rust
struct Person {
    name: String,
}

trait Greet {
    fn say_hello(&self);   // required method (no default)
    
	fn say_goodbye(&self) {  // traits can have default methods
        println!("Goodbye!");
    }
}

impl Greet for Person {
    fn say_hello(&self) {
        println!("Hello, my name is {}", self.name);
    }
}

fn main() {
    let p = Person { name: "Bob".into() };
    p.say_hello();
    p.say_goodbye();
}
```

#### operator interactions
- [[r trait]] implement how [[r struct]] interact with operators like in the following example

```rust
use std::ops::Add;

#[derive(Debug, Clone, Copy)]
struct Rect { width: u32, height: u32 }

impl Add for Rect {
    type Output = Rect;

    fn add(self, rhs: Rect) -> Rect {
        Rect {
            width:  self.width  + rhs.width,
            height: self.height + rhs.height,
        }
    }
}

fn main() {
    let a = Rect { width: 3, height: 4 };
    let b = Rect { width: 5, height: 6 };
    let c = a + b; // moves a and b
    println!("{:?}", c);
}
```

Tags: code rust
<!--ID: 1756383003742-->
END


START
Basic
what does the following [[rust]] snippet do and does it work?

```rust
impl MyTrait for MyStruct {}
```

Back: 
- if `MyTrait` has default implementations for everything, it will take over the default
- if `MyTrait` doesn't have defaults everywhere it wont compile
### trait
- in [[rust]] a [[r trait]] is the equivalent to an interface in [[python]] or java
- defines a set of methods (and sometimes constants or types) that a type must implement to "satisfy" that trait.

```rust
struct Person {
    name: String,
}

trait Greet {
    fn say_hello(&self);   // required method (no default)
    
	fn say_goodbye(&self) {  // traits can have default methods
        println!("Goodbye!");
    }
}

impl Greet for Person {
    fn say_hello(&self) {
        println!("Hello, my name is {}", self.name);
    }
}

fn main() {
    let p = Person { name: "Bob".into() };
    p.say_hello();
    p.say_goodbye();
}
```



Tags: code rust
<!--ID: 1756383003744-->
END

