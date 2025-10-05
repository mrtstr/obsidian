## pattern
- in [[rust]] a [[r pattern]] is a template that can be matched against a `value` to do one or both of the following
	- **Check its shape** (does this value fit?)
	- **Destructure it** (pull parts out into temp variables)
- the pattern is the definition of something like a [[r struct]], a [[r tuple]] or a [[r enum]] with values that can contain a literal (→ check of the `value` matches it) or a free variable (→ the variable will be temporarily defined as the data in the of the `value`)
- it can be used almost everywhere: `match`, `if let`, `while let`, `let`, `for` or for [[r generic type]]
### types of patterns
- check if value matches literal

```rust
match x {
    1 => println!("one"),
    _ => println!("anything else"), // matches everything else
}
```

- [[r range]] match: check is value is in [[r range]]

```rust
let x = 7;
match x {
    1..=5 => println!("between 1 and 5"),
    6..=10 => println!("between 6 and 10"),
    _ => println!("other"),
    // no condition so always true but value unsused
}
```

- temporary variable binding: there is no condition → `n` will be equal to `x`

```rust
match x {
    n => println!("matched {n}"), // binds x to n
}
```

- destructing [[r tuple]]: check of the values of the [[r tuple]] match the literal and if yes defile the variables

```rust
let pair = (0, -2);

match pair {
    (0, y) => println!("x is zero, y is {y}"),
    (x, 0) => println!("y is zero, x is {x}"),
    _ => println!("something else"), 
    // no condition so always true but value unsused
}
```

- destructing [[r struct]]

```rust
struct Point { x: i32, y: i32 }
let p = Point { x: 3, y: 7 };

match p {
    Point { x: 0, y } => println!("On Y axis at {y}"),
    Point { x, y: 0 } => println!("On X axis at {x}"),
    Point { x, y } => println!("({x},{y})"),
}
```

- pattern for null handling
```rust
let x = Some(5);

match x {
    Some(v) if v > 3 => println!("Greater than 3"),
    Some(v) => println!("Got {v}"),
    None => println!("Nothing"),
}
```

- [[r pattern]] for working with [[r enum]]

```rust
enum Message {
    Quit,
    Move { x: i32, y: i32 },
}

let msg = Message::Move { x: 10, y: 20 };

match msg {
    Message::Quit => println!("Quit"),
    Message::Move { x, y } => println!("Move to {x}, {y}"),
}
```

- [[r pattern]] with additional condition

```rust
let num = Some(4);

match num {
	Some(x) if x % 2 == 0 => println!("The number {x} is even"),
	Some(x) => println!("The number {x} is odd"),
	None => (),
}
```
### how they can be used


- matching for multiple patterns:

```rust

match expr {
	// block runs if expr matches PATTERN1
    PATTERN1 => {...},
    // block runs if expr matches PATTERN2
    PATTERN2 => {...},
    ...
    // block runs always because no condition
    _ => {...},
}


let num = 2;

match num {
    1 => println!("one"),
    2 | 3 => println!("two or three"),
    4..=10 => println!("between 4 and 10"),
    _ => println!("something else"),  // wildcard
}
```



- pattern matching for a single [[r pattern]]

```rust
if let PATTERN = expr {
    // block runs if expr matches PATTERN
}
if let None = x {
    println!("x is None");
}
if let Some(v) = x {
    println!("value = {v}");
}
```

- pattern used for assigning values by destructing [[r tuple]], [[r struct]] or [[r enum]]
- usually no condition is given, but it's possible to use a conditional pattern when an else block is defined, but else block has to diverge

```rust
let PATTERN = VALUE; 

let COND_PATTERN = EXPR else {
	// what to do if it doesn’t match
	// break, return or continue has to be called
};

let (x, y, z) = (1, 2, 3);  // tuple destructuring
println!("{x}, {y}, {z}");

struct Point { x: i32, y: i32 }
let p = Point { x: 10, y: 20 };

// destructure struct
let Point { x: a, y: b } = p;
println!("a={a}, b={b}");
```

- pattern matching in [[r loops]] with a [[r iterator]]

```rust
while let Some(v) = iter.next() {
	println!("Got {v}");
}
```


# anki

START
Basic
[[r pattern]] in [[rust]]
- concept
- where is it used
- basic examples:
	- simple range and literal matching
	- given a [[r tuple]] `(x, y)` write a pattern matching that checks if the point is on the X or Y axis and prints the other coordinate and if not say something
Back: 
## pattern
- in [[rust]] a [[r pattern]] is a template that can be matched against a `value` to do one or both of the following
	- **Check its shape** (does this value fit?)
	- **Destructure it** (pull parts out into temp variables)
- the pattern is the definition of something like a [[r struct]], a [[r tuple]] or a [[r enum]] with values that can contain a literal (→ check of the `value` matches it) or a free variable (→ the variable will be temporarily defined as the data in the of the `value`)
- it can be used almost everywhere: `match`, `if let`, `while let`, `let`, `for` or for [[r generic type]]
### types of patterns
- check if value matches literal

```rust
match x {
    1 => println!("one"),
    _ => println!("anything else"), // matches everything else
}
```

- [[r range]] match: check is value is in [[r range]]

```rust
let x = 7;
match x {
    1..=5 => println!("between 1 and 5"),
    6..=10 => println!("between 6 and 10"),
    _ => println!("other"),
    // no condition so always true but value unsused
}
```

- temporary variable binding: there is no condition → `n` will be equal to `x`

```rust
match x {
    n => println!("matched {n}"), // binds x to n
}
```

- destructing [[r tuple]]: check of the values of the [[r tuple]] match the literal and if yes defile the variables

```rust
let pair = (0, -2);

match pair {
    (0, y) => println!("x is zero, y is {y}"),
    (x, 0) => println!("y is zero, x is {x}"),
    _ => println!("something else"), 
    // no condition so always true but value unsused
}
```

- destructing [[r struct]]

```rust
struct Point { x: i32, y: i32 }
let p = Point { x: 3, y: 7 };

match p {
    Point { x: 0, y } => println!("On Y axis at {y}"),
    Point { x, y: 0 } => println!("On X axis at {x}"),
    Point { x, y } => println!("({x},{y})"),
}
```

- pattern for null handling
```rust
let x = Some(5);

match x {
    Some(v) if v > 3 => println!("Greater than 3"),
    Some(v) => println!("Got {v}"),
    None => println!("Nothing"),
}
```

- [[r pattern]] for working with [[r enum]]

```rust
enum Message {
    Quit,
    Move { x: i32, y: i32 },
}

let msg = Message::Move { x: 10, y: 20 };

match msg {
    Message::Quit => println!("Quit"),
    Message::Move { x, y } => println!("Move to {x}, {y}"),
}
```

- [[r pattern]] with additional condition

```rust
let num = Some(4);

match num {
	Some(x) if x % 2 == 0 => println!("The number {x} is even"),
	Some(x) => println!("The number {x} is odd"),
	None => (),
}
```
### how they can be used


- matching for multiple patterns:

```rust

match expr {
	// block runs if expr matches PATTERN1
    PATTERN1 => {...},
    // block runs if expr matches PATTERN2
    PATTERN2 => {...},
    ...
    // block runs always because no condition
    _ => {...},
}


let num = 2;

match num {
    1 => println!("one"),
    2 | 3 => println!("two or three"),
    4..=10 => println!("between 4 and 10"),
    _ => println!("something else"),  // wildcard
}
```



- pattern matching for a single [[r pattern]]

```rust
if let PATTERN = expr {
    // block runs if expr matches PATTERN
}
if let None = x {
    println!("x is None");
}
if let Some(v) = x {
    println!("value = {v}");
}
```

- pattern used for assigning values by destructing [[r tuple]], [[r struct]] or [[r enum]]
- usually no condition is given, but it's possible to use a conditional pattern when an else block is defined, but else block has to diverge

```rust
let PATTERN = VALUE; 

let COND_PATTERN = EXPR else {
	// what to do if it doesn’t match
	// break, return or continue has to be called
};

let (x, y, z) = (1, 2, 3);  // tuple destructuring
println!("{x}, {y}, {z}");

struct Point { x: i32, y: i32 }
let p = Point { x: 10, y: 20 };

// destructure struct
let Point { x: a, y: b } = p;
println!("a={a}, b={b}");
```

- pattern matching in [[r loops]]

```rust
while let Some(v) = iter.next() {
	println!("Got {v}");
}
```


Tags: code rust
<!--ID: 1756646909280-->
END


START
Basic
[[r pattern]] matching example
- write a [[r pattern]] matching that evaluates a condition and extracts values


```rust
let x = Some(5);

enum Message {
    Quit,
    Move { x: i32, y: i32 },
}

struct Point { x: i32, y: i32 }
```

Back: 

- pattern for null handling
```rust
let x = Some(5);

match x {
    Some(v) if v > 3 => println!("Greater than 3"),
    Some(v) => println!("Got {v}"),
    None => println!("Nothing"),
}
```

- [[r pattern]] for working with [[r enum]]

```rust
enum Message {
    Quit,
    Move { x: i32, y: i32 },
}

let msg = Message::Move { x: 10, y: 20 };

match msg {
    Message::Quit => println!("Quit"),
    Message::Move { x, y } => println!("Move to {x}, {y}"),
}
```

- destructing [[r struct]]

```rust
struct Point { x: i32, y: i32 }
let p = Point { x: 3, y: 7 };

match p {
    Point { x: 0, y } => println!("On Y axis at {y}"),
    Point { x, y: 0 } => println!("On X axis at {x}"),
    Point { x, y } => println!("({x},{y})"),
}
```

## pattern
- in [[rust]] a [[r pattern]] is a template that can be matched against a `value` to do one or both of the following
	- **Check its shape** (does this value fit?)
	- **Destructure it** (pull parts out into temp variables)
- the pattern is the definition of something like a [[r struct]], a [[r tuple]] or a [[r enum]] with values that can contain a literal (→ check of the `value` matches it) or a free variable (→ the variable will be temporarily defined as the data in the of the `value`)
- it can be used almost everywhere: `match`, `if let`, `while let`, `let`, `for` or for [[r generic type]]
### types of patterns
- check if value matches literal

```rust
match x {
    1 => println!("one"),
    _ => println!("anything else"), // matches everything else
}
```

- [[r range]] match: check is value is in [[r range]]

```rust
let x = 7;
match x {
    1..=5 => println!("between 1 and 5"),
    6..=10 => println!("between 6 and 10"),
    _ => println!("other"),
    // no condition so always true but value unsused
}
```

- temporary variable binding: there is no condition → `n` will be equal to `x`

```rust
match x {
    n => println!("matched {n}"), // binds x to n
}
```

- destructing [[r tuple]]: check of the values of the [[r tuple]] match the literal and if yes defile the variables

```rust
let pair = (0, -2);

match pair {
    (0, y) => println!("x is zero, y is {y}"),
    (x, 0) => println!("y is zero, x is {x}"),
    _ => println!("something else"), 
    // no condition so always true but value unsused
}
```




### how they can be used


- matching for multiple patterns:

```rust

match expr {
	// block runs if expr matches PATTERN1
    PATTERN1 => {...},
    // block runs if expr matches PATTERN2
    PATTERN2 => {...},
    ...
    // block runs always because no condition
    _ => {...},
}


let num = 2;

match num {
    1 => println!("one"),
    2 | 3 => println!("two or three"),
    4..=10 => println!("between 4 and 10"),
    _ => println!("something else"),  // wildcard
}
```



- pattern matching for a single [[r pattern]]

```rust
if let PATTERN = expr {
    // block runs if expr matches PATTERN
}
if let None = x {
    println!("x is None");
}
if let Some(v) = x {
    println!("value = {v}");
}
```

- pattern used for assigning values by destructing [[r tuple]], [[r struct]] or [[r enum]]
- usually no condition is given, but it's possible to use a conditional pattern when an else block is defined, but else block has to diverge

```rust
let PATTERN = VALUE; 

let COND_PATTERN = EXPR else {
	// what to do if it doesn’t match
	// break, return or continue has to be called
};

let (x, y, z) = (1, 2, 3);  // tuple destructuring
println!("{x}, {y}, {z}");

struct Point { x: i32, y: i32 }
let p = Point { x: 10, y: 20 };

// destructure struct
let Point { x: a, y: b } = p;
println!("a={a}, b={b}");
```

- pattern matching in [[r loops]]

```rust
while let Some(v) = iter.next() {
	println!("Got {v}");
}
```


Tags: code rust
<!--ID: 1756646909283-->
END


START
Basic
use case of [[r pattern]] in [[rust]]: general with concert example
- single conditional pattern matching with assignment
- multi conditional pattern matching with assignment
- assignment by destructing
- in [[r loops]]
Back: 

- matching for multiple patterns:

```rust

match expr {
	// block runs if expr matches PATTERN1
    PATTERN1 => {...},
    // block runs if expr matches PATTERN2
    PATTERN2 => {...},
    ...
    // block runs always because no condition
    _ => {...},
}


let num = 2;

match num {
    1 => println!("one"),
    2 | 3 => println!("two or three"),
    4..=10 => println!("between 4 and 10"),
    _ => println!("something else"),  // wildcard
}
```



- pattern matching for a single [[r pattern]]

```rust
if let PATTERN = expr {
    // block runs if expr matches PATTERN
}
if let None = x {
    println!("x is None");
}
if let Some(v) = x {
    println!("value = {v}");
}
```

- pattern used for assigning values by destructing [[r tuple]], [[r struct]] or [[r enum]]
- usually no condition is given, but it's possible to use a conditional pattern when an else block is defined, but else block has to diverge

```rust
let PATTERN = VALUE; 

let COND_PATTERN = EXPR else {
	// what to do if it doesn’t match
	// break, return or continue has to be called
};

let (x, y, z) = (1, 2, 3);  // tuple destructuring
println!("{x}, {y}, {z}");

struct Point { x: i32, y: i32 }
let p = Point { x: 10, y: 20 };

// destructure struct
let Point { x: a, y: b } = p;
println!("a={a}, b={b}");
```

- pattern matching in [[r loops]]

```rust
while let Some(v) = iter.next() {
	println!("Got {v}");
}
```

## pattern
- in [[rust]] a [[r pattern]] is a template that can be matched against a `value` to do one or both of the following
	- **Check its shape** (does this value fit?)
	- **Destructure it** (pull parts out into temp variables)
- the pattern is the definition of something like a [[r struct]], a [[r tuple]] or a [[r enum]] with values that can contain a literal (→ check of the `value` matches it) or a free variable (→ the variable will be temporarily defined as the data in the of the `value`)
- it can be used almost everywhere: `match`, `if let`, `while let`, `let`, `for` or for [[r generic type]]
### types of patterns
- check if value matches literal

```rust
match x {
    1 => println!("one"),
    _ => println!("anything else"), // matches everything else
}
```

- [[r range]] match: check is value is in [[r range]]

```rust
let x = 7;
match x {
    1..=5 => println!("between 1 and 5"),
    6..=10 => println!("between 6 and 10"),
    _ => println!("other"),
    // no condition so always true but value unsused
}
```

- temporary variable binding: there is no condition → `n` will be equal to `x`

```rust
match x {
    n => println!("matched {n}"), // binds x to n
}
```

- destructing [[r tuple]]: check of the values of the [[r tuple]] match the literal and if yes defile the variables

```rust
let pair = (0, -2);

match pair {
    (0, y) => println!("x is zero, y is {y}"),
    (x, 0) => println!("y is zero, x is {x}"),
    _ => println!("something else"), 
    // no condition so always true but value unsused
}
```

- destructing [[r struct]]

```rust
struct Point { x: i32, y: i32 }
let p = Point { x: 3, y: 7 };

match p {
    Point { x: 0, y } => println!("On Y axis at {y}"),
    Point { x, y: 0 } => println!("On X axis at {x}"),
    Point { x, y } => println!("({x},{y})"),
}
```

- pattern for null handling
```rust
let x = Some(5);

match x {
    Some(v) if v > 3 => println!("Greater than 3"),
    Some(v) => println!("Got {v}"),
    None => println!("Nothing"),
}
```

- [[r pattern]] for working with [[r enum]]

```rust
enum Message {
    Quit,
    Move { x: i32, y: i32 },
}

let msg = Message::Move { x: 10, y: 20 };

match msg {
    Message::Quit => println!("Quit"),
    Message::Move { x, y } => println!("Move to {x}, {y}"),
}
```



Tags: code rust
<!--ID: 1756646909285-->
END



START
Basic

write [[r pattern]] matching that get a [[r option]] with an int and prints if its odd, even or None

Back: 

- [[r pattern]] with additional condition

```rust
let num = Some(4);

match num {
	Some(x) if x % 2 == 0 => println!("The number {x} is even"),
	Some(x) => println!("The number {x} is odd"),
	None => (),
}
```

## pattern
- in [[rust]] a [[r pattern]] is a template that can be matched against a `value` to do one or both of the following
	- **Check its shape** (does this value fit?)
	- **Destructure it** (pull parts out into temp variables)
- the pattern is the definition of something like a [[r struct]], a [[r tuple]] or a [[r enum]] with values that can contain a literal (→ check of the `value` matches it) or a free variable (→ the variable will be temporarily defined as the data in the of the `value`)
- it can be used almost everywhere: `match`, `if let`, `while let`, `let`, `for` or for [[r generic type]]
### types of patterns
- check if value matches literal

```rust
match x {
    1 => println!("one"),
    _ => println!("anything else"), // matches everything else
}
```

- [[r range]] match: check is value is in [[r range]]

```rust
let x = 7;
match x {
    1..=5 => println!("between 1 and 5"),
    6..=10 => println!("between 6 and 10"),
    _ => println!("other"),
    // no condition so always true but value unsused
}
```

- temporary variable binding: there is no condition → `n` will be equal to `x`

```rust
match x {
    n => println!("matched {n}"), // binds x to n
}
```

- destructing [[r tuple]]: check of the values of the [[r tuple]] match the literal and if yes defile the variables

```rust
let pair = (0, -2);

match pair {
    (0, y) => println!("x is zero, y is {y}"),
    (x, 0) => println!("y is zero, x is {x}"),
    _ => println!("something else"), 
    // no condition so always true but value unsused
}
```

- destructing [[r struct]]

```rust
struct Point { x: i32, y: i32 }
let p = Point { x: 3, y: 7 };

match p {
    Point { x: 0, y } => println!("On Y axis at {y}"),
    Point { x, y: 0 } => println!("On X axis at {x}"),
    Point { x, y } => println!("({x},{y})"),
}
```

- pattern for null handling
```rust
let x = Some(5);

match x {
    Some(v) if v > 3 => println!("Greater than 3"),
    Some(v) => println!("Got {v}"),
    None => println!("Nothing"),
}
```

- [[r pattern]] for working with [[r enum]]

```rust
enum Message {
    Quit,
    Move { x: i32, y: i32 },
}

let msg = Message::Move { x: 10, y: 20 };

match msg {
    Message::Quit => println!("Quit"),
    Message::Move { x, y } => println!("Move to {x}, {y}"),
}
```

- [[r pattern]] with additional condition

```rust
let num = Some(4);

match num {
	Some(x) if x % 2 == 0 => println!("The number {x} is even"),
	Some(x) => println!("The number {x} is odd"),
	None => (),
}
```

Tags: code rust
<!--ID: 1759683035826-->
END