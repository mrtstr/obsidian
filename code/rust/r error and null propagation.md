## error and null propagation
- errors can be propagated back with the following pattern thru the functions that works with [[r option]] and [[r result]]
- `std::fs::File::open("user.txt")?` is syntactic sugar for the following

```rust
let file = match std::fs::File::open("user.txt") {
    Ok(f) => f,
    Err(e) => return Err(e),
};
```

- that means the following function reads a [[r string]] and returns it as a [[r result]] if everything worked and if there is an error somewhere during opening the file or reading the file it immediately returns the error 

```rust
fn read_username() -> std::io::Result<String> {
    let mut s = String::new();
    std::fs::File::open("user.txt")?.read_to_string(&mut s)?;
    Ok(s)
}
```

this is equivalent for the following

```rust
fn read_username() -> io::Result<String> {
    // Try opening the file
    let mut file = match File::open("user.txt") {
        Ok(f) => f,
        Err(e) => return Err(e),
    };

    // Prepare the buffer
    let mut s = String::new();

    // Try reading into it
    match file.read_to_string(&mut s) {
        Ok(_) => Ok(s),
        Err(e) => Err(e),
    }
}
```

# ------------


![[r option#option]]

![[r result#result]]


# anki

START
Basic
 [[r error and null propagation]] in [[rust]]
 - concept
 - example

Back: 

## error and null propagation
- errors can be propagated back with the following pattern thru the functions that works with [[r option]] and [[r result]]
- `std::fs::File::open("user.txt")?` is syntactic sugar for the following

```rust
let file = match std::fs::File::open("user.txt") {
    Ok(f) => f,
    Err(e) => return Err(e),
};
```

- that means the following function reads a [[r string]] and returns it as a [[r result]] if everything worked and if there is an error somewhere during opening the file or reading the file it immediately returns the error 

```rust
fn read_username() -> std::io::Result<String> {
    let mut s = String::new();
    std::fs::File::open("user.txt")?.read_to_string(&mut s)?;
    Ok(s)
}
```

this is equivalent for the following

```rust
fn read_username() -> io::Result<String> {
    // Try opening the file
    let mut file = match File::open("user.txt") {
        Ok(f) => f,
        Err(e) => return Err(e),
    };

    // Prepare the buffer
    let mut s = String::new();

    // Try reading into it
    match file.read_to_string(&mut s) {
        Ok(_) => Ok(s),
        Err(e) => Err(e),
    }
}
```


__________________

### result
- in [[rust]] the [[r enum]] [[r result]] is similar to [[r option]]

```rust
enum Result<T, E> {
    Ok(T),   // success, contains value of type T
    Err(E),  // failure, contains error info
}
```
### option
- [[r enum]] for handling values that can be none (see [[r null handling]])
- null values are handled with the [[r enum]] [[r option]] than can be `Some` or `None`

```rust
enum Option<T> { Some(T), None }
```

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
<!--ID: 1757057806853-->
END


START
Basic
what does the following do?
rewrite it using [[r pattern]] matching explicitly

```rust
fn read_username() -> std::io::Result<String> {
    let mut s = String::new();
    std::fs::File::open("user.txt")?.read_to_string(&mut s)?;
    Ok(s)
}
```

Back: 

## error and null propagation
- errors can be propagated back with the following pattern thru the functions that works with [[r option]] and [[r result]]
- `std::fs::File::open("user.txt")?` is syntactic sugar for the following

```rust
let file = match std::fs::File::open("user.txt") {
    Ok(f) => f,
    Err(e) => return Err(e),
};
```

- that means the following function reads a [[r string]] and returns it as a [[r result]] if everything worked and if there is an error somewhere during opening the file or reading the file it immediately returns the error 

```rust
fn read_username() -> std::io::Result<String> {
    let mut s = String::new();
    std::fs::File::open("user.txt")?.read_to_string(&mut s)?;
    Ok(s)
}
```

this is equivalent for the following

```rust
fn read_username() -> io::Result<String> {
    // Try opening the file
    let mut file = match File::open("user.txt") {
        Ok(f) => f,
        Err(e) => return Err(e),
    };

    // Prepare the buffer
    let mut s = String::new();

    // Try reading into it
    match file.read_to_string(&mut s) {
        Ok(_) => Ok(s),
        Err(e) => Err(e),
    }
}
```


__________________

### result
- in [[rust]] the [[r enum]] [[r result]] is similar to [[r option]]

```rust
enum Result<T, E> {
    Ok(T),   // success, contains value of type T
    Err(E),  // failure, contains error info
}
```
### option
- [[r enum]] for handling values that can be none (see [[r null handling]])
- null values are handled with the [[r enum]] [[r option]] than can be `Some` or `None`

```rust
enum Option<T> { Some(T), None }
```

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
<!--ID: 1757057806857-->
END