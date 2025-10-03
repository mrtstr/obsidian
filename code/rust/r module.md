### module
- in [[rust]] a [[r module]] is like a namespace for code organization inside a [[r crate]]
- it groups related items ([[r function]], [[r struct]], [[r trait]],  submodules, …)

inline [[r module]]:

```rust
mod math {
    pub fn add(a: i32, b: i32) -> i32 { a + b }
}
```

file based [[r module]] (code organized in separate files):

```rust
// lib.rs
mod math; // Rust will look for `math.rs` or `math/mod.rs`
```

```rust
// math.rs
pub fn add(a: i32, b: i32) -> i32 { a + b }
```

usage:

```rust
let x = math::add(2, 3);
```

#### full names

```rust
mod front_of_house {
	pub mod hosting {
		pub fn add_to_waitlist() {}
	}
}
```

- to use a [[r function]] from the crate itself for example it can be referenced by its relative name using `super` or by its absolute name using `crate`

```rust
crate::front_of_house::hosting::add_to_waitlist();
super::front_of_house::hosting::add_to_waitlist();
```

- for an installed [[r crate]] the function would be references by `<name of installed crate>::front_of_house::hosting::add_to_waitlist();`

#### imports and shortcuts
- it remove boilerplate, it's possible to create a shortcut with the `use` keyword for a specific scope to a [[r function]] or a [[r module]]

```rust
// shortcut to a module
mod customer {
	use super::front_of_house::hosting;
	pub fn eat_at_restaurant() {
		hosting::add_to_waitlist();
	}
}
// shortcut to a specific function
mod customer {
	use super::front_of_house::hosting::eat_at_restaurant;
	pub fn eat_at_restaurant() {
		eat_at_restaurant();
	}
}
```

```rust
// import std::io as a module and Write
use std::io::{self, Write}; //brings std::io and Write in
// import everything from a module
use std::collections::*;
```

- to make the imports for a [[r library crates]] more user-friendly shortcuts can be created in the root file to make them importable directly from the root crate without the full name of potentially multiple sub modules

# anki

START
Basic
[[r module]] in [[rust]]
- concept
- how to use functions from sub-modules inside the same [[r crate]] (2) and installed crates?
- how to remove boilerplate related to longs chains of sub modules names
- how to make to imports of [[r library crates]] user-friendly?
- example: from to create `std::io` and `Write` from `std::io`? How to import everything from `std::collections`?
Back: 

### module
- in [[rust]] a [[r module]] is like a namespace for code organization inside a [[r crate]]
- it groups related items ([[r function]], [[r struct]], [[r trait]],  submodules, …)

inline [[r module]]:

```rust
mod math {
    pub fn add(a: i32, b: i32) -> i32 { a + b }
}
```

file based [[r module]] (code organized in separate files):

```rust
// lib.rs
mod math; // Rust will look for `math.rs` or `math/mod.rs`
```

```rust
// math.rs
pub fn add(a: i32, b: i32) -> i32 { a + b }
```

usage:

```rust
let x = math::add(2, 3);
```

#### full names

```rust
mod front_of_house {
	pub mod hosting {
		pub fn add_to_waitlist() {}
	}
}
```

- to use a [[r function]] from the crate itself for example it can be referenced by its relative name using `super` or by its absolute name using `crate`

```rust
crate::front_of_house::hosting::add_to_waitlist();
super::front_of_house::hosting::add_to_waitlist();
```

- for an installed [[r crate]] the function would be references by `<name of installed crate>::front_of_house::hosting::add_to_waitlist();`

#### imports and shortcuts
- it remove boilerplate, it's possible to create a shortcut with the `use` keyword for a specific scope to a [[r function]] or a [[r module]]

```rust
// shortcut to a module
mod customer {
	use super::front_of_house::hosting;
	pub fn eat_at_restaurant() {
		hosting::add_to_waitlist();
	}
}
// shortcut to a specific function
mod customer {
	use super::front_of_house::hosting::eat_at_restaurant;
	pub fn eat_at_restaurant() {
		eat_at_restaurant();
	}
}
```

```rust
// import std::io as a module and Write
use std::io::{self, Write}; //brings std::io and Write in
// import everything from a module
use std::collections::*;
```

- to make the imports for a [[r library crates]] more user-friendly shortcuts can be created in the root file to make them importable directly from the root crate without the full name of potentially multiple sub modules

_____________
## project organization
- in [[rust]] a code base can be organized in 

1) [[r workspace]] : Groups multiple packages, shares one `Cargo.lock` + `target/`.
2) [[r package]]: defined by its `Cargo.toml`
3) [[r crate]]: compilation unit with single root file
4) [[r module]]: namespace organization inside a crate


```
Workspace (optional)
├── Cargo.toml   (with [workspace])
├── package-a/   (a package = has its own Cargo.toml)
│   ├── Cargo.toml
│   └── src/
│       ├── lib.rs   (library crate root)
│       │   ├── mod1.rs    (module inside the library crate)
│       │   └── mod2/
│       │       └── mod.rs (nested module)
│       ├── main.rs  (binary crate root)
│       └── bin/     (extra binaries, each a crate)
│           ├── tool1.rs (binary crate)
│           └── tool2.rs (binary crate)
└── package-b/
    ├── Cargo.toml
    └── src/
        └── lib.rs (library crate root with modules)
```

### workspace
- a [[r workspace]] in [[rust]] is a group of multiple [[r package|packages]] that share a `Cargo.toml` file a `target` folder
- it can be used for sharing dependencies and metadata

example:

```toml
[workspace]
members = [
	"cli_example",
	"wrapped_example_rs"
]
# Optional: prevent Cargo from searching for crates in other folders
exclude = [
	"pysrc", # your Python code
	"*.ipynb", # notebooks
]
# (optional) you can set shared dependencies if needed
[workspace.dependencies]
anyhow = "1.0"
polars = "0.39"

# (optional) shared metadata: can be inherented by the packages
# if <parameter>.workspace = true is set
[workspace.package]
version = "0.1.0"
edition = "2021"
authors = ["M S <ms@example.com>"]
```

### package
- a [[r package]] in [[rust]] is defined by a `Cargo.toml` and is an entity that can be uploaded to `crates.io`
- it can be part of a [[r workspace]]
- it can contain multiple [[r crate|crates]] but only one [[r library crates|library crates]] (but potentially multiple binary crates)

```
my_pkg/              ← package (Cargo.toml here)
├── Cargo.toml
└── src/
    ├── lib.rs       ← library crate root
    ├── main.rs      ← binary crate root
    └── bin/
        ├── tool1.rs ← another binary crate
        └── tool2.rs ← another binary crate
```

### crate
- a [[r crate]] is a compilation unit in [[rust]]
- it has a single root file that can be either a `main.rs` or a `lib.rs` (depending on if it's an executable binary crate or a library crate)
- a [[r crate]] is part of a [[r package]] and can contain multiple [[r module]]

#### crate types
- there are executable `bin` crates that are the final output of the [[compiler#linking]] process
- [[r library crates]] that are created during the [[compiler#code generation]] and are intended to be used in other applications (dynamic/static, rust/non-rust)
- [[r macro]] crates for shipping [[r macro]] (compiler plugins)

### module
- in [[rust]] a [[r module]] is like a namespace for code organization inside a [[r crate]]
- it groups related items ([[r function]], [[r struct]], [[r trait]],  submodules, …)

inline [[r module]]:

```rust
mod math {
    pub fn add(a: i32, b: i32) -> i32 { a + b }
}
```

file based [[r module]] (code organized in separate files):

```rust
// lib.rs
mod math; // Rust will look for `math.rs` or `math/mod.rs`
```

```rust
// math.rs
pub fn add(a: i32, b: i32) -> i32 { a + b }
```

usage:

```rust
let x = math::add(2, 3);
```

Tags: code rust
<!--ID: 1759514068985-->
END