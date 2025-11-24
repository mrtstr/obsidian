### dynamic collections
- Two patterns for holding heterogeneous collections in [[rust]]

```rust
struct Dog {
    name: String,
    breed: String,
}

#[derive(Debug)]
struct Cat {
    name: String,
    lives_left: u8,
}
```

|Feature|Trait Object (`dyn`)|Enum|
|---|---|---|
|**Dispatch**|Runtime (vtable)|Compile-time|
|**Memory**|Heap (`Box`)|Stack|
|**Extensible**|✅ Yes|❌ No (closed set)|
|**Performance**|Good|Excellent|
|**Use case**|Plugins, unknown types|Fixed types, games|
#### Pattern 1: Trait Objects (Dynamic Dispatch)
**Use when:** You need extensibility and don't know all types at compile time (plugins, frameworks).

```rust
trait Animal {}
impl Animal for Dog {}
impl Animal for Cat {}

type AnimalsDynamic = Vec<Box<dyn Animal>>

let my_animals: AnimalsDynamic = vec![
    Box::new(Dog { name: "Buddy".into(), breed: "Beagle".into() }),
    Box::new(Cat { name: "Whiskers".into(), lives_left: 7 }),
];

```

#### Pattern 2: Enum (Tagged Union)
**Use when:** You have a fixed, known set of types and want maximum performance.

```rust
enum AnimalEnum {
    Cat(Cat),
    Dog(Dog),
}

type AnimalsEnum = Vec<AnimalEnum>

let my_animals: AnimalsEnum = vec![
    AnimalEnum::Dog(Dog { name: "Max".into(), breed: "Husky".into() }),
    AnimalEnum::Cat(Cat { name: "Felix".into(), lives_left: 9 }),
];
```

# anki

START
Basic
### dynamic collections
- Two patterns for holding heterogeneous collections in [[rust]]

```rust
struct Dog {
    name: String,
    breed: String,
}

#[derive(Debug)]
struct Cat {
    name: String,
    lives_left: u8,
}
```

- where the it stored?
- which is faster?
- which is more flexible/explainable?
Back: 


| Feature         | Trait Object (`dyn`)   | Enum               |
| --------------- | ---------------------- | ------------------ |
| **Dispatch**    | Runtime (vtable)       | Compile-time       |
| **Memory**      | Heap (`Box`)           | Stack              |
| **Extensible**  | ✅ Yes                  | ❌ No (closed set)  |
| **Performance** | Good                   | Excellent          |
| **Use case**    | Plugins, unknown types | Fixed types, games |
#### Pattern 1: Trait Objects (Dynamic Dispatch)
- **Use when:** You need extensibility and don't know all types at compile time (plugins, frameworks).
- can be extended after compilation because the [[r trait]] `Animal` can be implemented for other [[r struct]]

```rust
trait Animal {}
impl Animal for Dog {}
impl Animal for Cat {}

type AnimalsDynamic = Vec<Box<dyn Animal>>

let my_animals: AnimalsDynamic = vec![
    Box::new(Dog { name: "Buddy".into(), breed: "Beagle".into() }),
    Box::new(Cat { name: "Whiskers".into(), lives_left: 7 }),
];

```

#### Pattern 2: Enum (Tagged Union)
- **Use when:** You have a fixed, known set of types and want maximum performance.
- cannot be extended because the [[r enum]] `AnimalEnum` is fixed

```rust
enum AnimalEnum {
    Cat(Cat),
    Dog(Dog),
}

type AnimalsEnum = Vec<AnimalEnum>

let my_animals: AnimalsEnum = vec![
    AnimalEnum::Dog(Dog { name: "Max".into(), breed: "Husky".into() }),
    AnimalEnum::Cat(Cat { name: "Felix".into(), lives_left: 9 }),
];
```

Tags: rust code WS2526
<!--ID: 1763972174682-->
END