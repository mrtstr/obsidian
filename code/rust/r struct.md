## struct
- in [[rust]] a [[r struct]] is a custom [[r data type]] that groups values and [[r function]] to gather under one name
- similar to a [[python]] [[py object]] but without [[py inheritance]]

### adding functions
- an `impl` block is used to attach [[r function]] to a [[r struct]] (there can be multiple of these blocks)
- they take `&self` as argument to immutable access its data and `&mut self` for mutable access or take [[r ownership]] with `self`
- where there is no self [[r reference]] its a [[r associated function]]

```rust
struct Rectangle {
    width: u32,
    height: u32,
}

impl Rectangle {
    // Method: takes an immutable reference to self
    fn area(&self) -> u32 {
        self.width * self.height
    }

    // Method: takes a mutable reference to self
    fn make_square(&mut self) {
        self.height = self.width;
    }

    // Associated function: no self
    fn new(width: u32, height: u32) -> Self {
        Self { width, height }
    }
}

fn main() {
    let mut rect = Rectangle::new(10, 20);

    println!("Area = {}", rect.area()); // calls method
    rect.make_square();                 // modifies self
    println!("Now square: {}x{}", rect.width, rect.height);
}
```

### names struct
- [[r field]] have names

```rust
struct Rectangle {
    width: u32,
    height: u32,
}

fn main() {
    let r = Rectangle { width: 10, height: 20 };
    println!("{} x {}", r.width, r.height);
}
```
### tuple struct
- [[r field]] don't have names and only positions
- like [[py tuple]]

```rust
struct Color(u8, u8, u8);   // RGB
struct Point(f64, f64);

fn main() {
    let c = Color(255, 100, 50);
    let p = Point(0.5, 1.2);

    println!("R = {}", c.0);
    println!("Point y = {}", p.1);
}
```
### unit struct
- no [[r field]]
- used as [[r marker]]

```rust
struct Marker;

impl Marker {
    fn hello() {
        println!("I’m just a marker!");
    }
}

fn main() {
    let m = Marker;  // no fields
    Marker::hello();
}
```
# anki

START
Basic
[[r struct]] in [[rust]]
- concept
- 3 concepts how functions can be added (regarding self access)
- 3 types of [[r struct]] with example
Back: 
## struct
- in [[rust]] a [[r struct]] is a custom [[r data type]] that groups values and [[r function]] to gather under one name
- similar to a [[python]] [[py object]] but without [[py inheritance]]
### adding functions
- an `impl` block is used to attach [[r function]] to a [[r struct]] (there can be multiple of these blocks)
- they take `&self` as argument to immutable access its data and `&mut self` for mutable access or take [[r ownership]] with `self`
- where there is no self [[r reference]] its a [[r associated function]]


```rust
struct Rectangle {
    width: u32,
    height: u32,
}

impl Rectangle {
    // Method: takes an immutable reference to self
    fn area(&self) -> u32 {
        self.width * self.height
    }

    // Method: takes a mutable reference to self
    fn make_square(&mut self) {
        self.height = self.width;
    }

    // Associated function: no self
    fn new(width: u32, height: u32) -> Self {
        Self { width, height }
    }
}

fn main() {
    let mut rect = Rectangle::new(10, 20);

    println!("Area = {}", rect.area()); // calls method
    rect.make_square();                 // modifies self
    println!("Now square: {}x{}", rect.width, rect.height);
}
```

### names struct
- [[r field]] have names

```rust
struct Rectangle {
    width: u32,
    height: u32,
}

fn main() {
    let r = Rectangle { width: 10, height: 20 };
    println!("{} x {}", r.width, r.height);
}
```
### tuple struct
- [[r field]] don't have names and only positions
- like [[py tuple]]

```rust
struct Color(u8, u8, u8);   // RGB
struct Point(f64, f64);

fn main() {
    let c = Color(255, 100, 50);
    let p = Point(0.5, 1.2);

    println!("R = {}", c.0);
    println!("Point y = {}", p.1);
}
```
### unit struct
- no [[r field]]
- used as [[r marker]]

```rust
struct Marker;

impl Marker {
    fn hello() {
        println!("I’m just a marker!");
    }
}

fn main() {
    let m = Marker;  // no fields
    Marker::hello();
}
```

Tags: code rust
<!--ID: 1756052658850-->
END