### dynamic dispatch
- implement something for a [[r generic type]] that implement a certain [[r trait]]
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

# ----------

![[r object safe traits#object safe traits]]

# anki

START
Basic
[[r dynamic dispatch]]
- definition
- code examples
- pro and cons with [[r static dispatch]]
- when can it be used?

Back: 
### dynamic dispatch
- implement something for a [[r generic type]] that implement a certain [[r trait]]
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

### object safe traits
- A [[r trait]] is **object safe** if the [[compiler]] can create a `dyn Trait` from it, meaning all trait-object-visible methods don’t depend on knowing the concrete `Self` type or its size, and don’t have their own generic type parameters.


❌ Not object-safe: generic methods:

```rust
trait Factory {
    fn make<T>(&self) -> T;  // generic over T
}
```

❌ Not object-safe by default: returning `Self`

```rust
trait CloneLike {
    fn clone_like(&self) -> Self; // returns Self
}
```

`Self` might be any size — a trait object doesn’t know which concrete type it points to, so it can’t know how big the returned value is. This makes the method **not callable** on `dyn CloneLike`, so the trait is not object safe _unless_ you restrict that method to sized types

Tags: code rust
<!--ID: 1763979331653-->
END
