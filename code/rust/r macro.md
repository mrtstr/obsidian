### macro
- in [[rust]] a [[r macro]] is a compile time meta programming feature → code that writes code
- expanded during the [[compiler|compilation process]] → works on token level and not on [[r data type]]

```
Rust Macros
│
├── Declarative macros (pattern → expansion)
│   │
│   ├── macro_rules!      (classic)
│   │     ├── println!   → built-in, expands to formatting code
│   │     ├── vec!       → builds a Vec<T>
│   │     └── dbg!       → debug-print values
│   │
│   └── macro (Macros 2.0, newer syntax, still stabilizing)
│
└── Procedural macros (need proc_macro crate, transform TokenStreams)
    │
    ├── Function-like      #[proc_macro]
    │     ├── sqlx::query! → compiles SQL at build time
    │     └── custom macros you write → my_macro!(...)
    │
    ├── Derive             #[proc_macro_derive]
    │     ├── #[derive(Debug)]     → built-in
    │     ├── #[derive(Serialize)] → from Serde
    │     └── #[derive(Clone)]     → built-in
    │
    └── Attribute           #[proc_macro_attribute]
          ├── #[route(GET, "/")] → Rocket / Actix web routing
          ├── #[tokio::main]     → turns async fn main into runtime entry
          └── #[test]            → marks a test function
```
#### declarative macros
- replace something with something else on a token level (pattern → expansion) 
- not interaction with the token as data
- predefined examples `println!`, `vec!`
- two API: `macro_rules` and `macro`
##### `macro_rules!` API
- syntax is similar to [[r pattern]] matching but instead of `match` the keyword `macro_rules!` is used to define the replacement rules

```rust
macro_rules! say_hello {
    () => {
        println!("Hello!");
    };
}

fn main() {
    say_hello!(); // expands into println!("Hello!");
}
```

```rust
// Define a macro
macro_rules! make_tuple {
    // Pattern: two expressions separated by a comma
    ($a:expr, $b:expr) => {
        ($a, $b)  // expands into a tuple
    };
}

fn main() {
    let t = make_tuple!(10, 20); 
    println!("{:?}", t); // prints (10, 20)
}
```

##### macro API
- newer api to define a `declarative macros` in function style

```
macro add($a:expr, $b:expr) {
    $a + $b
}
```


#### procedural macros
- run actual [[rust]] code at compile time → interaction with predefined data possible
- written as separate crates because they need compiler hooks
- `proc_macro` is part of [[rust]] [[r std]] and allows processing rust code during [[compiler|compile time]]

```rust
use proc_macro::TokenStream;

#[proc_macro]
pub fn shout(input: TokenStream) -> TokenStream {
    // Convert input tokens into a string
    let input_str = input.to_string();

    // Transform to uppercase
    let upper = input_str.to_uppercase();

    // Return Rust code: println!("UPPER")
    format!("println!(\"{}\")", upper).parse().unwrap()
    // "println!(\"HELLO\")".parse::<TokenStream>() 
    // -> Result<TokenStream>
    // .unwrap() -> TokenStream
}
```


# -----------------



# anki

START
Basic
[[r macro]]
- concept
- two types with difference and syntax
Back: 
### macro
- in [[rust]] a [[r macro]] is a compile time meta programming feature → code that writes code
- expanded during the [[compiler|compilation process]] → works on token level and not on [[r data type]]

```
Rust Macros
│
├── Declarative macros (pattern → expansion)
│   │
│   ├── macro_rules!      (classic)
│   │     ├── println!   → built-in, expands to formatting code
│   │     ├── vec!       → builds a Vec<T>
│   │     └── dbg!       → debug-print values
│   │
│   └── macro (Macros 2.0, newer syntax, still stabilizing)
│
└── Procedural macros (need proc_macro crate, transform TokenStreams)
    │
    ├── Function-like      #[proc_macro]
    │     ├── sqlx::query! → compiles SQL at build time
    │     └── custom macros you write → my_macro!(...)
    │
    ├── Derive             #[proc_macro_derive]
    │     ├── #[derive(Debug)]     → built-in
    │     ├── #[derive(Serialize)] → from Serde
    │     └── #[derive(Clone)]     → built-in
    │
    └── Attribute           #[proc_macro_attribute]
          ├── #[route(GET, "/")] → Rocket / Actix web routing
          ├── #[tokio::main]     → turns async fn main into runtime entry
          └── #[test]            → marks a test function
```
#### declarative macros
- replace something with something else on a token level (pattern → expansion) 
- not interaction with the token as data
- predefined examples `println!`, `vec!`
- two API: `macro_rules` and `macro`
##### `macro_rules!` API
- syntax is similar to [[r pattern]] matching but instead of `match` the keyword `macro_rules!` is used to define the replacement rules

```rust
macro_rules! say_hello {
    () => {
        println!("Hello!");
    };
}

fn main() {
    say_hello!(); // expands into println!("Hello!");
}
```

```rust
// Define a macro
macro_rules! make_tuple {
    // Pattern: two expressions separated by a comma
    ($a:expr, $b:expr) => {
        ($a, $b)  // expands into a tuple
    };
}

fn main() {
    let t = make_tuple!(10, 20); 
    println!("{:?}", t); // prints (10, 20)
}
```

##### macro API
- newer api to define a `declarative macros` in function style

```
macro add($a:expr, $b:expr) {
    $a + $b
}
```


#### procedural macros
- run actual [[rust]] code at compile time → interaction with predefined data possible
- written as separate crates because they need compiler hooks
- `proc_macro` is part of [[rust]] [[r std]] and allows processing rust code during [[compiler|compile time]]

```rust
use proc_macro::TokenStream;

#[proc_macro]
pub fn shout(input: TokenStream) -> TokenStream {
    // Convert input tokens into a string
    let input_str = input.to_string();

    // Transform to uppercase
    let upper = input_str.to_uppercase();

    // Return Rust code: println!("UPPER")
    format!("println!(\"{}\")", upper).parse().unwrap()
    // "println!(\"HELLO\")".parse::<TokenStream>() 
    // -> Result<TokenStream>
    // .unwrap() -> TokenStream
}
```

Tags: code rust
<!--ID: 1757170528283-->
END



START
Basic
[[r macro]] that converts string to upper case
- to which category does it belong, and why is this category best suited?
Back: 


#### procedural macros
- run actual [[rust]] code at compile time → interaction with predefined data possible
- written as separate crates because they need compiler hooks
- `proc_macro` is part of [[rust]] [[r std]] and allows processing rust code during [[compiler|compile time]]

```rust
use proc_macro::TokenStream;

#[proc_macro]
pub fn shout(input: TokenStream) -> TokenStream {
    // Convert input tokens into a string
    let input_str = input.to_string();

    // Transform to uppercase
    let upper = input_str.to_uppercase();

    // Return Rust code: println!("UPPER")
    format!("println!(\"{}\")", upper).parse().unwrap()
    // "println!(\"HELLO\")".parse::<TokenStream>() 
    // -> Result<TokenStream>
    // .unwrap() -> TokenStream
}
```
### macro
- in [[rust]] a [[r macro]] is a compile time meta programming feature → code that writes code
- expanded during the [[compiler|compilation process]] → works on token level and not on [[r data type]]

```
Rust Macros
│
├── Declarative macros (pattern → expansion)
│   │
│   ├── macro_rules!      (classic)
│   │     ├── println!   → built-in, expands to formatting code
│   │     ├── vec!       → builds a Vec<T>
│   │     └── dbg!       → debug-print values
│   │
│   └── macro (Macros 2.0, newer syntax, still stabilizing)
│
└── Procedural macros (need proc_macro crate, transform TokenStreams)
    │
    ├── Function-like      #[proc_macro]
    │     ├── sqlx::query! → compiles SQL at build time
    │     └── custom macros you write → my_macro!(...)
    │
    ├── Derive             #[proc_macro_derive]
    │     ├── #[derive(Debug)]     → built-in
    │     ├── #[derive(Serialize)] → from Serde
    │     └── #[derive(Clone)]     → built-in
    │
    └── Attribute           #[proc_macro_attribute]
          ├── #[route(GET, "/")] → Rocket / Actix web routing
          ├── #[tokio::main]     → turns async fn main into runtime entry
          └── #[test]            → marks a test function
```
#### declarative macros
- replace something with something else on a token level (pattern → expansion) 
- not interaction with the token as data
- predefined examples `println!`, `vec!`
- two API: `macro_rules` and `macro`
##### `macro_rules!` API
- syntax is similar to [[r pattern]] matching but instead of `match` the keyword `macro_rules!` is used to define the replacement rules

```rust
macro_rules! say_hello {
    () => {
        println!("Hello!");
    };
}

fn main() {
    say_hello!(); // expands into println!("Hello!");
}
```

```rust
// Define a macro
macro_rules! make_tuple {
    // Pattern: two expressions separated by a comma
    ($a:expr, $b:expr) => {
        ($a, $b)  // expands into a tuple
    };
}

fn main() {
    let t = make_tuple!(10, 20); 
    println!("{:?}", t); // prints (10, 20)
}
```

##### macro API
- newer api to define a `declarative macros` in function style

```
macro add($a:expr, $b:expr) {
    $a + $b
}
```


#### procedural macros
- run actual [[rust]] code at compile time → interaction with predefined data possible
- written as separate crates because they need compiler hooks
- `proc_macro` is part of [[rust]] [[r std]] and allows processing rust code during [[compiler|compile time]]

```rust
use proc_macro::TokenStream;

#[proc_macro]
pub fn shout(input: TokenStream) -> TokenStream {
    // Convert input tokens into a string
    let input_str = input.to_string();

    // Transform to uppercase
    let upper = input_str.to_uppercase();

    // Return Rust code: println!("UPPER")
    format!("println!(\"{}\")", upper).parse().unwrap()
    // "println!(\"HELLO\")".parse::<TokenStream>() 
    // -> Result<TokenStream>
    // .unwrap() -> TokenStream
}
```

Tags: code rust
<!--ID: 1757170528287-->
END


START
Basic
[[r macro]] examples (with two different APIs)
- that adds two numbers 
- makes a tuple

- to which category do they belong, and why is this category best suited?
Back: 

```
macro add($a:expr, $b:expr) {
    $a + $b
}
```


```rust
// Define a macro
macro_rules! make_tuple {
    // Pattern: two expressions separated by a comma
    ($a:expr, $b:expr) => {
        ($a, $b)  // expands into a tuple
    };
}

fn main() {
    let t = make_tuple!(10, 20); 
    println!("{:?}", t); // prints (10, 20)
}
```
### macro
- in [[rust]] a [[r macro]] is a compile time meta programming feature → code that writes code
- expanded during the [[compiler|compilation process]] → works on token level and not on [[r data type]]

```
Rust Macros
│
├── Declarative macros (pattern → expansion)
│   │
│   ├── macro_rules!      (classic)
│   │     ├── println!   → built-in, expands to formatting code
│   │     ├── vec!       → builds a Vec<T>
│   │     └── dbg!       → debug-print values
│   │
│   └── macro (Macros 2.0, newer syntax, still stabilizing)
│
└── Procedural macros (need proc_macro crate, transform TokenStreams)
    │
    ├── Function-like      #[proc_macro]
    │     ├── sqlx::query! → compiles SQL at build time
    │     └── custom macros you write → my_macro!(...)
    │
    ├── Derive             #[proc_macro_derive]
    │     ├── #[derive(Debug)]     → built-in
    │     ├── #[derive(Serialize)] → from Serde
    │     └── #[derive(Clone)]     → built-in
    │
    └── Attribute           #[proc_macro_attribute]
          ├── #[route(GET, "/")] → Rocket / Actix web routing
          ├── #[tokio::main]     → turns async fn main into runtime entry
          └── #[test]            → marks a test function
```
#### declarative macros
- replace something with something else on a token level (pattern → expansion) 
- not interaction with the token as data
- predefined examples `println!`, `vec!`
- two API: `macro_rules` and `macro`
##### `macro_rules!` API
- syntax is similar to [[r pattern]] matching but instead of `match` the keyword `macro_rules!` is used to define the replacement rules

```rust
macro_rules! say_hello {
    () => {
        println!("Hello!");
    };
}

fn main() {
    say_hello!(); // expands into println!("Hello!");
}
```

```rust
// Define a macro
macro_rules! make_tuple {
    // Pattern: two expressions separated by a comma
    ($a:expr, $b:expr) => {
        ($a, $b)  // expands into a tuple
    };
}

fn main() {
    let t = make_tuple!(10, 20); 
    println!("{:?}", t); // prints (10, 20)
}
```

##### macro API
- newer api to define a `declarative macros` in function style

```
macro add($a:expr, $b:expr) {
    $a + $b
}
```


#### procedural macros
- run actual [[rust]] code at compile time → interaction with predefined data possible
- written as separate crates because they need compiler hooks
- `proc_macro` is part of [[rust]] [[r std]] and allows processing rust code during [[compiler|compile time]]

```rust
use proc_macro::TokenStream;

#[proc_macro]
pub fn shout(input: TokenStream) -> TokenStream {
    // Convert input tokens into a string
    let input_str = input.to_string();

    // Transform to uppercase
    let upper = input_str.to_uppercase();

    // Return Rust code: println!("UPPER")
    format!("println!(\"{}\")", upper).parse().unwrap()
    // "println!(\"HELLO\")".parse::<TokenStream>() 
    // -> Result<TokenStream>
    // .unwrap() -> TokenStream
}
```

Tags: code rust
<!--ID: 1757170528290-->
END