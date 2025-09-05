## error handling
- in [[rust]] there are two concepts for error handling

in the [[rust]] ecosystem there are [[r crate]] for conveniently handling errors:
- `thiserror` → easy custom error enums.
- `anyhow` and `eyre` → ergonomic error handling in applications, with backtraces
### recoverable errors
- for things that may happen in normal operation like file missing
- represented as [[r result]] return type

![[r result#result]]

- can be propagated easily thruw the function calls

![[r error and null propagation#error and null propagation]]
### unrecoverable errors
- errors does to a programming mistakes, like out-of-bounds access
- should not be handled and lead to a crash of the [[li thread]] or [[li process]]
- can be called explicitly with [[r panic]] or will be raised implicit when something like `index out of bounds` happens

```rust
panic!("Something went terribly wrong");
```

- [[r panic]] can be cached with `panic::catch_unwind` but its not recommended for most cases

```rust
use std::panic;

let result = panic::catch_unwind(|| {
	println!("About to panic...");
	panic!("Boom!");
});
```
# anki

START
Basic
[[r error handling]] in [[rust]]
- two concepts
- how to work convenient with errors: [[r crate]] and patterns

Back: 
## error handling
- in [[rust]] there are two concepts for error handling

in the [[rust]] ecosystem there are [[r crate]] for conveniently handling errors:
- `thiserror` → easy custom error enums.
- `anyhow` and `eyre` → ergonomic error handling in applications, with backtraces
### recoverable errors
- for things that may happen in normal operation like file missing
- represented as [[r result]] return type

#### result
- in [[rust]] the [[r enum]] [[r result]] is similar to [[r option]] used for [[r error handling]]
- used as return value for operations that can go wrong like reading a file (e.g. file not found) or processing or a dataframe

```rust
enum Result<T, E> {
    Ok(T),   // success, contains value of type T
    Err(E),  // failure, contains error info
}
```

- can be propagated easily thru the function calls

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
### unrecoverable errors
- errors does to a programming mistakes, like out-of-bounds access
- should not be handled and lead to a crash of the [[li thread]] or [[li process]]
- can be called explicitly with [[r panic]] or will be raised implicit when something like `index out of bounds` happens

```rust
panic!("Something went terribly wrong");
```

- [[r panic]] can be cached with `panic::catch_unwind` but its not recommended for most cases

```rust
use std::panic;

let result = panic::catch_unwind(|| {
	println!("About to panic...");
	panic!("Boom!");
});
```


Tags: code rust
<!--ID: 1757057806860-->
END


