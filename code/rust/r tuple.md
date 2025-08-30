### tuple
- fixed size collection of values with heterogeneous [[r data type]]
- lives on the [[li stack]] (its values too)
- can be defined as mutable or immutable but the size can't change even if mutable
- the mutability of its values depends on their [[r data type]]
- a [[py list comprehension]] style definition does not work → use [[r vec]] instead
- its not possible to access the `ith` value with `i` being a variable itself → use [[r array]] or [[r vec]]
#### syntax
- can be declared using `()`

```rust
let tup1: (i32, f64, &str) = (42, 3.14, "hello");
let mut tup2 = (1, 2.0, String::from("hi"));
```

- elements can be accessed using `.`

```rust
tup.0 = 10;
tup.1 = 3.14;
```


# anki

START
Basic
[[r tuple]] in [[rust]]
- concept
- [[li memory]] segment
- mutability

syntax
- how to define it
- how to define it [[py list comprehension]] style
- how to access values and access them dynamically
Back: 
### tuple
- fixed size collection of values with heterogeneous [[r data type]]
- lives on the [[li stack]] (its values too)
- can be defined as mutable or immutable, but the size can't change even if mutable
- the mutability of its values depends on their [[r data type]]
- a [[py list comprehension]] style definition does not work → use [[r vec]] instead
- its not possible to access the `ith` value with `i` being a variable itself → use [[r array]] or [[r vec]]
#### syntax
- can be declared using `()`

```rust
let tup1: (i32, f64, &str) = (42, 3.14, "hello");
let mut tup2 = (1, 2.0, String::from("hi"));
```

- elements can be accessed using `.`

```rust
tup.0 = 10;
tup.1 = 3.14;
```
Tags: code rust
<!--ID: 1756537963337-->
END
