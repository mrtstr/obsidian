## generic type

- [[r static dispatch]]: 
	- functions replicated at [[r compile time]]
	- larger binary s but faster at runtime
	- makes sense when the function is not used for too many different types
- [[r dynamic dispatch]]
	- looked up at runtime
	- smaller binary's but slight overhead at runtime
	- works only on [[r object safe traits]]

### examples

```rust
trait Draw {
    fn draw(&self);
}

struct Button;
struct Label;

impl Draw for Button {
    fn draw(&self) { println!("Button"); }
}
impl Draw for Label {
    fn draw(&self) { println!("Label"); }
}
```

- for functions variables

```rust
// Static dispatch
fn render<T: Draw>(widget: T) {
    widget.draw();
}

// dynamic dispatch
fn render2(widget: impl Draw) {
    widget.draw();
}
```

- for type definitions

```rust
// Static via generics
struct App<T: Draw> {
    widget: T,
}

// Dynamic via trait object
// doent work because the size of draw is not known at compile time
struct AppDyn {
    widget: dyn Draw,
}

// needs a pointer
struct AppDyn {
    widget: Box<dyn Draw>,
}

```


- inside containers

```rust
fn feed_animal<T: Eater>(animal: &T) {
    animal.eat();
}

fn feed_animal_dyn(animal: &dyn Eater) {
    animal.eat();
}

let dog = Dog { name: String::from("Buddy") };
let cat = Cat { name: String::from("Whiskers") };
let animals: Vec<&dyn Eater> = vec![&dog, &cat];

feed_animal(&dog);  // ✅ works, T = Dog
feed_animal(&cat);  // ✅ works, T = Cat

for animal in animals {
    feed_animal(animal);
    //    ^^^^^^^^^^^^^ ❌ does NOT compile
}

feed_animal_dyn(&dog);  // ✅ works, &Dog coerces to &dyn Eater
feed_animal_dyn(&cat);  // ✅ works, &Cat coerces to &dyn Eater

for animal in animals {
    feed_animal_dyn(animal);  // ✅ works, animal: &dyn Eater
}
```

The line `feed_animal(animal)` inside the loop tries to infer `T` from the argument type:
- `animal` has type `&dyn Eater`.
- `feed_animal` takes `&T`, so the compiler unifies `&T` with `&dyn Eater` → `T = dyn Eater`.
But:
- Generic type params are **`Sized` by default** (`T: Eater` is really `T: Eater + Sized`).
- `dyn Eater` is **unsized**, so `T = dyn Eater` violates the implicit `Sized` bound.

![[r dynamic dispatch#dynamic dispatch]]

![[r static dispatch#static dispatch]]


# anki

START
Basic
two options how to implement a function for a [[r generic type]]
- with differences and pros and cons
- implement the following examples using both options
	- write a function that can take everything that implements `Draw`
	- write an [[r struct]] `App` that can have a widget that as to implement `Draw`

```rust
trait Draw {
    fn draw(&self);
}

struct Button;
struct Label;

impl Draw for Button {
    fn draw(&self) { println!("Button"); }
}
impl Draw for Label {
    fn draw(&self) { println!("Label"); }
}
```

Back: 
## generic type

- [[r static dispatch]]: 
	- functions replicated at [[r compile time]]
	- larger binary s but faster at runtime
	- makes sense when the function is not used for too many different types
- [[r dynamic dispatch]]
	- looked up at runtime
	- smaller binary's but slight overhead at runtime
	- works only on [[r object safe traits]]

### examples


- for functions variables

```rust
// Static dispatch
fn render<T: Draw>(widget: T) {
    widget.draw();
}

// dynamic dispatch
fn render2(widget: impl Draw) {
    widget.draw();
}
```

- for type definitions

```rust
// Static via generics
struct App<T: Draw> {
    widget: T,
}

// Dynamic via trait object
// doent work because the size of draw is not known at compile time
struct AppDyn {
    widget: dyn Draw,
}

// needs a pointer
struct AppDyn {
    widget: Box<dyn Draw>,
}

```

- inside containers


```rust
fn feed_animal<T: Eater>(animal: &T) {
    animal.eat();
}

fn feed_animal_dyn(animal: &dyn Eater) {
    animal.eat();
}

let dog = Dog { name: String::from("Buddy") };
let cat = Cat { name: String::from("Whiskers") };
let animals: Vec<&dyn Eater> = vec![&dog, &cat];

feed_animal(&dog);  // ✅ works, T = Dog
feed_animal(&cat);  // ✅ works, T = Cat

for animal in animals {
    feed_animal(animal);
    //    ^^^^^^^^^^^^^ ❌ does NOT compile
}

feed_animal_dyn(&dog);  // ✅ works, &Dog coerces to &dyn Eater
feed_animal_dyn(&cat);  // ✅ works, &Cat coerces to &dyn Eater

for animal in animals {
    feed_animal_dyn(animal);  // ✅ works, animal: &dyn Eater
}
```

The line `feed_animal(animal)` inside the loop tries to infer `T` from the argument type:
- `animal` has type `&dyn Eater`.
- `feed_animal` takes `&T`, so the compiler unifies `&T` with `&dyn Eater` → `T = dyn Eater`.
But:
- Generic type params are **`Sized` by default** (`T: Eater` is really `T: Eater + Sized`).
- `dyn Eater` is **unsized**, so `T = dyn Eater` violates the implicit `Sized` bound.
### dynamic dispatch
- implement something for all [[r struct]] and [[r enum]] that implement a certain [[r trait]]
- decided at [[r run time]] and not at [[r compile time]] like [[r static dispatch]] 
	→ slightly slower but smaller binary's
- only works with [[r object safe traits]]
#### syntax example

```rust
trait Draw {
    fn draw(&self);
}

fn render_dyn(x: &dyn Draw) {  // dynamic dispatch
    x.draw();                  // uses a vtable at runtime
}


struct AppDyn {
    widget: Box<dyn Draw>,
}
```

## static dispatch
- [[r function]] that work with a [[r generic type]] can be implemented as follows
- at [[r compile time]] the [[r rustc]] creates multiple versions of the functions for all [[r data type]] of values it is used for 

```rust
fn identity<T>(x: T) -> T { x }

let a = identity(10);                // T = i32
let b = identity(String::from("x")); // T = String
```

#### constraints
- it's possible to define contains, like in this example the [[r data type]] has to implement the [[r trait]] `XYZ` or otherwise it won't compile

```rust
fn identity<T: XYZ>(x: T) -> T {
    x // valid only for types that implement XYZ
}
```

- the constraints can be made explicit like in the following equivalent example

```rust
fn identity<T>(x: T) -> T
where
    T: XYZ,
{
    x
}
```

Tags: code rust
<!--ID: 1763979331657-->
END


# anki

START
Basic
- does the following code work and if not how to do it instead?

```rust
fn feed_animal<T: Eater>(animal: &T) {
    animal.eat();
}

let dog = Dog { name: String::from("Buddy") };
let cat = Cat { name: String::from("Whiskers") };
let animals: Vec<&dyn Eater> = vec![&dog, &cat];

feed_animal(&dog);
feed_animal(&cat);

for animal in animals {
    feed_animal(animal);
}

```

Back: 

```rust
fn feed_animal<T: Eater>(animal: &T) {
    animal.eat();
}

fn feed_animal_dyn(animal: &dyn Eater) {
    animal.eat();
}

let dog = Dog { name: String::from("Buddy") };
let cat = Cat { name: String::from("Whiskers") };
let animals: Vec<&dyn Eater> = vec![&dog, &cat];

feed_animal(&dog);  // ✅ works, T = Dog
feed_animal(&cat);  // ✅ works, T = Cat

for animal in animals {
    feed_animal(animal);
    //    ^^^^^^^^^^^^^ ❌ does NOT compile
}

feed_animal_dyn(&dog);  // ✅ works, &Dog coerces to &dyn Eater
feed_animal_dyn(&cat);  // ✅ works, &Cat coerces to &dyn Eater

for animal in animals {
    feed_animal_dyn(animal);  // ✅ works, animal: &dyn Eater
}
```

The line `feed_animal(animal)` inside the loop tries to infer `T` from the argument type:
- `animal` has type `&dyn Eater`.
- `feed_animal` takes `&T`, so the compiler unifies `&T` with `&dyn Eater` → `T = dyn Eater`.
But:
- Generic type params are **`Sized` by default** (`T: Eater` is really `T: Eater + Sized`).
- `dyn Eater` is **unsized**, so `T = dyn Eater` violates the implicit `Sized` bound.
## generic type

- [[r static dispatch]]: 
	- functions replicated at [[r compile time]]
	- larger binary s but faster at runtime
	- makes sense when the function is not used for too many different types
- [[r dynamic dispatch]]
	- looked up at runtime
	- smaller binary's but slight overhead at runtime
	- works only on [[r object safe traits]]

### examples


- for functions variables

```rust
// Static dispatch
fn render<T: Draw>(widget: T) {
    widget.draw();
}

// dynamic dispatch
fn render2(widget: impl Draw) {
    widget.draw();
}
```

- for type definitions

```rust
// Static via generics
struct App<T: Draw> {
    widget: T,
}

// Dynamic via trait object
// doent work because the size of draw is not known at compile time
struct AppDyn {
    widget: dyn Draw,
}

// needs a pointer
struct AppDyn {
    widget: Box<dyn Draw>,
}

```



### dynamic dispatch
- implement something for all [[r struct]] and [[r enum]] that implement a certain [[r trait]]
- decided at [[r run time]] and not at [[r compile time]] like [[r static dispatch]] 
	→ slightly slower but smaller binary's
- only works with [[r object safe traits]]
#### syntax example

```rust
trait Draw {
    fn draw(&self);
}

fn render_dyn(x: &dyn Draw) {  // dynamic dispatch
    x.draw();                  // uses a vtable at runtime
}


struct AppDyn {
    widget: Box<dyn Draw>,
}
```

## static dispatch
- [[r function]] that work with a [[r generic type]] can be implemented as follows
- at [[r compile time]] the [[r rustc]] creates multiple versions of the functions for all [[r data type]] of values it is used for 

```rust
fn identity<T>(x: T) -> T { x }

let a = identity(10);                // T = i32
let b = identity(String::from("x")); // T = String
```

#### constraints
- it's possible to define contains, like in this example the [[r data type]] has to implement the [[r trait]] `XYZ` or otherwise it won't compile

```rust
fn identity<T: XYZ>(x: T) -> T {
    x // valid only for types that implement XYZ
}
```

- the constraints can be made explicit like in the following equivalent example

```rust
fn identity<T>(x: T) -> T
where
    T: XYZ,
{
    x
}
```

Tags: code rust
<!--ID: 1763982709987-->
END
