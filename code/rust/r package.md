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