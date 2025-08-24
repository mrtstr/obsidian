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


# anki

START
Basic
- concept in [[rust]] that is equivalent to a static/class function in [[python]] with examples on how to declare and use it

Back: 
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
<!--ID: 1756052658837-->
END