### lifetime annotations
- needed in cases where the borrow checker can't automatically infer the lifetime of the [[r reference]]
- a lifetime is a scope in which a [[r reference]] is valid

- in the following it would not be needed because it's clear the lifetime of the input reference is equal to the lifetime of the output reference

```rust
fn first(s: &str) -> &str { s }
```

- in the function `longest` the borrows checker does not know if the lifetime of the output is equal to the lifetime of `s1` or `s2` so it needs a lifetime annotation:
- the following means the lifetime of the returned reference is as most as long as the lifetime of the input with the shorter lifetime (lifetime of `output` >= min(lifetime of `s1`, lifetime of `s2`))

```rust
fn longest<'a>(s1: &'a str, s2: &'a str) -> &'a str {
    if s1.len() > s2.len() {
        s1
    } else {
        s2
    }
}
```

- when working with [[r struct]] that holds a reference we need the following to ensure that the [[r struct]] can't outlive the [[r reference]] it holds

```rust
struct Book<'a> {
    title: &'a str,
}
```


# anki

START
Basic
- what is wrong with the following function?
- explain the concept behind it and how to fix it

```rust
fn longest(s1: &str, s2: &str) -> &str {
    if s1.len() > s2.len() {
        s1
    } else {
        s2
    }
}
```

Back: 
### lifetime annotations
- needed in cases where the borrow checker can't automatically infer the lifetime of the [[r reference]]
- a lifetime is a scope in which a [[r reference]] is valid

- in the following it would not be needed because it's clear the lifetime of the input reference is equal to the lifetime of the output reference

```rust
fn first(s: &str) -> &str { s }
```

- in the function `longest` the borrows checker does not know if the lifetime of the output is equal to the lifetime of `s1` or `s2` so it needs a lifetime annotation:
- the following means the lifetime of the returned reference is as most as long as the lifetime of the input with the shorter lifetime (lifetime of `output` >= min(lifetime of `s1`, lifetime of `s2`))

```rust
fn longest<'a>(s1: &'a str, s2: &'a str) -> &'a str {
    if s1.len() > s2.len() {
        s1
    } else {
        s2
    }
}
```

- when working with [[r struct]] that holds a reference we need the following to ensure that the stuct can't outive the [[r reference]] it holds

```rust
struct Book<'a> {
    title: &'a str,
}
```



Tags: code rust
<!--ID: 1759603319826-->
END