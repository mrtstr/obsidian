### string
- [[r smart pointer]] and [[r container]] which is basically a wrapped version of [[r vec]] with type `u8`

#### declaring it

```rust
let s1 = String::new();                // empty
// uses the From trait implementation: String::from(&str)
let s2 = String::from("hello");        // from &str
// uses the ToString trait (auto-implemented for all types that implement Display)
// &str implements Display, so this works
let s3 = "world".to_string();          // from literal
// uses the Into trait (which is auto-implemented from From)
// here &str -> String, type of s4 clarifies target
let s4: String = "hi".into();          // From/Into
```

#### extending it
```rust
let mut s = String::from("foo");

s.push('!');           // add char
s.push_str(" bar");    // add &str
s.insert(0, 'H');      // insert at index
s.replace("bar", "baz"); // returns new String
s = s.replace("foo", "bar");
```

#### removing

```rust
let mut s = String::from("abcdef");

s.pop();               // removes last char
s.remove(0);           // removes char at index
s.truncate(3);         // keep only first 3 chars
s.clear();             // empty string
```

#### combining them

```rust
let s1 = String::from("hello");
let s2 = String::from("world");

// Using + (moves left-hand side!)
let s3 = s1 + " " + &s2;

// format! macro (no moves, preferred)
let s4 = format!("{} {}", "hello", "world");
```

# anki

START
Basic
[[r string]] in [[rust]]
- concept
- how to declare it (4 with differences)
- how to concat strings (3)
Back: 
### string
- [[r smart pointer]] and [[r container]] which is basically a wrapped version of [[r vec]] with type `u8`

#### declaring it

```rust
let s1 = String::new();                // empty
// uses the From trait implementation: String::from(&str)
let s2 = String::from("hello");        // from &str
// uses the ToString trait (auto-implemented for all types that implement Display)
// &str implements Display, so this works
let s3 = "world".to_string();          // from literal
// uses the Into trait (which is auto-implemented from From)
// here &str -> String, type of s4 clarifies target
let s4: String = "hi".into();          // From/Into
```

#### extending it

```rust
let mut s = String::from("foo");

s.push('!');           // add char
s.push_str(" bar");    // add &str
s.insert(0, 'H');      // insert at index
s.replace("bar", "baz"); // returns new String
s = s.replace("foo", "bar");
```

#### removing

```rust
let mut s = String::from("abcdef");

s.pop();               // removes last char
s.remove(0);           // removes char at index
s.truncate(3);         // keep only first 3 chars
s.clear();             // empty string
```

#### combining them

```rust
let s1 = String::from("hello");
let s2 = String::from("world");

// Using + (moves left-hand side!)
let s3 = s1 + " " + &s2;

// format! macro (no moves, preferred)
let s4 = format!("{} {}", "hello", "world");
```

Tags: code rust
<!--ID: 1756627337936-->
END