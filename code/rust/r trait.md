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

#### traits as return types
- it's possible to define the return type of functions by defining the traits if implements

```rust
fn returns_summarizable(switch: bool) -> impl Summary {
    if switch {
        NewsArticle {
            headline: ...
        }
    } else {
        SocialPost {
            username: ...
        }
    }
}
```

#### implementing traits for traits
- it's possible to implement [[r trait]] for a [[r trait]] like in the following example

```rust
impl<T: Display> ToString for T {
    // --snip--
}
```
# anki

START
Basic
[[r trait]] in [[rust]]
- concept
- how to define it
- example traits as return types
- example traits for traits
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

#### traits as return types
- it's possible to define the return type of functions by defining the traits if implements

```rust
fn returns_summarizable(switch: bool) -> impl Summary {
    if switch {
        NewsArticle {
            headline: ...
        }
    } else {
        SocialPost {
            username: ...
        }
    }
}
```

#### implementing traits for traits
- it's possible to implement [[r trait]] for a [[r trait]] like in the following example

```rust
impl<T: Display> ToString for T {
    // --snip--
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

START
Basic
[[r trait]] in [[rust]]
- how to define the return type of function by its traits?
- how to define a trait for another trait?

Back: 

#### traits as return types
- it's possible to define the return type of functions by defining the traits if implements

```rust
fn returns_summarizable(switch: bool) -> impl Summary {
    if switch {
        NewsArticle {
            headline: ...
        }
    } else {
        SocialPost {
            username: ...
        }
    }
}
```

#### implementing traits for traits
- it's possible to implement [[r trait]] for a [[r trait]] like in the following example

```rust
impl<T: Display> ToString for T {
    // --snip--
}
```

____________
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

#### traits as return types
- it's possible to define the return type of functions by defining the traits if implements

```rust
fn returns_summarizable(switch: bool) -> impl Summary {
    if switch {
        NewsArticle {
            headline: ...
        }
    } else {
        SocialPost {
            username: ...
        }
    }
}
```

#### implementing traits for traits
- it's possible to implement [[r trait]] for a [[r trait]] like in the following example

```rust
impl<T: Display> ToString for T {
    // --snip--
}
```

Tags: code rust
<!--ID: 1759603319832-->
END