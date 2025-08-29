### enum
- in [[rust]] a [[r enum]] can be one of a list of [[r data type]]
- its a group with of [[r data type]] with an `or` relationship while a [[r struct]] is a group of [[r field]] with an `and` relationship

```rust
enum Shape {
    Circle(f64),                  // tuple style (radius)
    Rectangle { w: f64, h: f64 }, // struct style
}
impl Shape {
	const dim: i32 = 2;

    fn area(&self) -> f64 {
        match self {
            Shape::Circle(r) => std::f64::consts::PI * r * r,
            Shape::Rectangle { w, h } => w * h,
        }
    }
}
let c = Shape::Circle(1.0);
```

- can have [[r function]] and [[r associated function]] and constants (in read only [[li data segment]])
- can implement [[r trait]]


# anki

START
Basic
[[r enum]]
- concept
- difference and similarity to [[r struct]]
- example how to use it

Back: 
### enum
- in [[rust]] a [[r enum]] can be one of a list of [[r data type]]
- its a group with of [[r data type]] with an `or` relationship while a [[r struct]] is a group of [[r field]] with an `and` relationship

```rust
enum Shape {
    Circle(f64),                  // tuple style (radius)
    Rectangle { w: f64, h: f64 }, // struct style
}
impl Shape {
	const dim: i32 = 2;

    fn area(&self) -> f64 {
        match self {
            Shape::Circle(r) => std::f64::consts::PI * r * r,
            Shape::Rectangle { w, h } => w * h,
        }
    }
}
let c = Shape::Circle(1.0);
```

- can have [[r function]] and [[r associated function]] and constants (in read only [[li data segment]])
- can implement [[r trait]]

Tags: code rust
<!--ID: 1756383003758-->
END


START
Basic
[[r enum]]
- implement the example `shape` which can be a Circle or a Rectangle and has a area function

Back: 
### enum
- in [[rust]] a [[r enum]] can be one of a list of [[r data type]]
- its a group with of [[r data type]] with an `or` relationship while a [[r struct]] is a group of [[r field]] with an `and` relationship

```rust
enum Shape {
    Circle(f64),                  // tuple style (radius)
    Rectangle { w: f64, h: f64 }, // struct style
}
impl Shape {
	const dim: i32 = 2;

    fn area(&self) -> f64 {
        match self {
            Shape::Circle(r) => std::f64::consts::PI * r * r,
            Shape::Rectangle { w, h } => w * h,
        }
    }
}
let c = Shape::Circle(1.0);
```

- can have [[r function]] and [[r associated function]] and constants (in read only [[li data segment]])
- can implement [[r trait]]

Tags: code rust
<!--ID: 1756449686236-->
END
