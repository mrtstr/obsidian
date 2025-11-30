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

### multiple generic types
- It's possible to have multiple [[r generic type]]
- this means `T: std::ops::Add<Output = T>` the input [[r data type]] has to implement the `Add` [[r trait]] and `T` is the [[r data type]] of the output of the add operation

```rust
fn pair<A, B>(a: A, b: B) -> (A, B) { (a, b) }
let i=1;
let j=10;
pair(j, i)
```



```rust
fn add_all<T: std::ops::Add<Output = T>, U: std::ops::Add<Output = U>>(x: T, y: T, u: U, v: U) -> (T, U) {
    (x + y, u + v)
}
```

### static dispatch: syntactic sugar
- for function argument  types and return types [[r static dispatch]] can be implemented using the `impl` keyword
- the following functions are equivalent

```rust
fn my_func1<T: MyTrait>(x: T) { /* ... */ }
fn my_func1(x: impl MyTrait) { /* ... */ }


fn my_func2<T: MyTrait>() -> T { /* ... */ }
fn my_func2()  -> impl MyTrait { /* ... */ }
```

- when `impl` appears multiple times it they are potentially different each time

```rust
// 1) Same type
fn same_type<T: MyTrait>(x: T, y: T) { /* ... */ }

// 2) Potentially different types
fn maybe_diff<T: MyTrait, U: MyTrait>(x: T, y: U) { /* ... */ }

// 3) impl version ≈ (2)
fn impl_version(x: impl MyTrait, y: impl MyTrait) { /* ... */ }
```

- in the following example the compiler rejects the second because the return type would be undefined because it don't have to be equivalent like in the first case

```rust
fn my_func3<T: MyTrait>(x: T)  -> T { /* ... */ }
fn my_func3(x: impl MyTrait) -> impl MyTrait { /* ... */ }
// ❌ rejected
```

- `impl Trait` in return position must be the **outermost** type thus the following doesn't work

```rust
fn foo() -> Vec<impl MyTrait> { /* ... */ }
// ❌ rejected
fn foo<T: MyTrait>() -> Vec<T> { /* ... */ }
//works
```
# anki

START
Basic
which of the following examples works and if not why?

```rust
fn my_func1<T: MyTrait>(x: T) { /* ... */ }
fn my_func1(x: impl MyTrait) { /* ... */ }
fn my_func2<T: MyTrait>() -> T { /* ... */ }
fn my_func2()  -> impl MyTrait { /* ... */ }
fn my_func3<T: MyTrait>(x: T)  -> T { /* ... */ }
fn my_func3(x: impl MyTrait) -> impl MyTrait { /* ... */ }
fn foo() -> Vec<impl MyTrait> { /* ... */ }
fn foo<T: MyTrait>() -> Vec<T> { /* ... */ }
```

- implement the function `f` without using the `impl` keyword

```rust
fn f(x: impl MyTrait, y: impl MyTrait) { /* ... */ }
```

Back: 
### static dispatch: syntactic sugar
- for function argument types and return types [[r static dispatch]] can be implemented using the `impl` keyword
- the following functions are equivalent

```rust
fn my_func1<T: MyTrait>(x: T) { /* ... */ }
fn my_func1(x: impl MyTrait) { /* ... */ }


fn my_func2<T: MyTrait>() -> T { /* ... */ }
fn my_func2()  -> impl MyTrait { /* ... */ }
```

- when `impl` appears multiple times it they are potentially different each time

```rust
// 1) Same type
fn same_type<T: MyTrait>(x: T, y: T) { /* ... */ }

// 2) Potentially different types
fn maybe_diff<T: MyTrait, U: MyTrait>(x: T, y: U) { /* ... */ }

// 3) impl version ≈ (2)
fn maybe_diff(x: impl MyTrait, y: impl MyTrait) { /* ... */ }
```

- in the following example the compiler rejects the second because the return type would be undefined because it don't have to be equivalent like in the first case

```rust
fn my_func3<T: MyTrait>(x: T)  -> T { /* ... */ }
fn my_func3(x: impl MyTrait) -> impl MyTrait { /* ... */ }
// ❌ rejected
```

- `impl Trait` in return position must be the **outermost** type thus the following doesn't work

```rust
fn foo() -> Vec<impl MyTrait> { /* ... */ }
// ❌ rejected
fn foo<T: MyTrait>() -> Vec<T> { /* ... */ }
//works
```
Tags: code rust
<!--ID: 1764496843813-->
END

START
Basic
two versions how to implement [[r static dispatch]] for functions arguments and return types
- equivalent examples
- examples where just one works

Back: 
### static dispatch: syntactic sugar
- for function argument types and return types [[r static dispatch]] can be implemented using the `impl` keyword
- the following functions are equivalent

```rust
fn my_func1<T: MyTrait>(x: T) { /* ... */ }
fn my_func1(x: impl MyTrait) { /* ... */ }


fn my_func2<T: MyTrait>() -> T { /* ... */ }
fn my_func2()  -> impl MyTrait { /* ... */ }
```

- when `impl` appears multiple times it they are potentially different each time

```rust
// 1) Same type
fn same_type<T: MyTrait>(x: T, y: T) { /* ... */ }

// 2) Potentially different types
fn maybe_diff<T: MyTrait, U: MyTrait>(x: T, y: U) { /* ... */ }

// 3) impl version ≈ (2)
fn impl_version(x: impl MyTrait, y: impl MyTrait) { /* ... */ }
```

- in the following example the compiler rejects the second because the return type would be undefined because it don't have to be equivalent like in the first case

```rust
fn my_func3<T: MyTrait>(x: T)  -> T { /* ... */ }
fn my_func3(x: impl MyTrait) -> impl MyTrait { /* ... */ }
// ❌ rejected
```

- `impl Trait` in return position must be the **outermost** type thus the following doesn't work

```rust
fn foo() -> Vec<impl MyTrait> { /* ... */ }
// ❌ rejected
fn foo<T: MyTrait>() -> Vec<T> { /* ... */ }
//works
```

Tags: code rust
<!--ID: 1764496843816-->
END

START
Basic
functions that can take multiple data types in [[rust]]
- concept
- 2 ways how to specify it
- what happens during [[r compile time]]
- how is it used

Back: 
- [[r static dispatch]] (2 versions): 
	- functions replicated at [[r compile time]]
	- larger binary s but faster at runtime
	- makes sense when the function is not used for too many different types
- [[r dynamic dispatch]]
	- looked up at runtime
	- smaller binary's but slight overhead at runtime
	- works only on [[r object safe traits]]
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


### static dispatch: syntactic sugar
- for function argument types and return types [[r static dispatch]] can be implemented using the `impl` keyword
- the following functions are equivalent

```rust
fn my_func1<T: MyTrait>(x: T) { /* ... */ }
fn my_func1(x: impl MyTrait) { /* ... */ }


fn my_func2<T: MyTrait>() -> T { /* ... */ }
fn my_func2()  -> impl MyTrait { /* ... */ }
```

- when `impl` appears multiple times it they are potentially different each time

```rust
// 1) Same type
fn same_type<T: MyTrait>(x: T, y: T) { /* ... */ }

// 2) Potentially different types
fn maybe_diff<T: MyTrait, U: MyTrait>(x: T, y: U) { /* ... */ }

// 3) impl version ≈ (2)
fn impl_version(x: impl MyTrait, y: impl MyTrait) { /* ... */ }
```

- in the following example the compiler rejects the second because the return type would be undefined because it don't have to be equivalent like in the first case

```rust
fn my_func3<T: MyTrait>(x: T)  -> T { /* ... */ }
fn my_func3(x: impl MyTrait) -> impl MyTrait { /* ... */ }
// ❌ rejected
```

- `impl Trait` in return position must be the **outermost** type thus the following doesn't work

```rust
fn foo() -> Vec<impl MyTrait> { /* ... */ }
// ❌ rejected
fn foo<T: MyTrait>() -> Vec<T> { /* ... */ }
//works
```
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
Tags: code rust
<!--ID: 1756383003751-->
END


START
Basic
difference between `dyn` and `impl` in [[rust]]
Back: 

`dyn` implements [[r dynamic dispatch]] while `impl` is syntactic sugar for [[r static dispatch]]

- [[r static dispatch]] (2 versions): 
	- functions replicated at [[r compile time]]
	- larger binary s but faster at runtime
	- makes sense when the function is not used for too many different types
- [[r dynamic dispatch]]
	- looked up at runtime
	- smaller binary's but slight overhead at runtime
	- works only on [[r object safe traits]]
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


### static dispatch: syntactic sugar
- for function argument types and return types [[r static dispatch]] can be implemented using the `impl` keyword
- the following functions are equivalent

```rust
fn my_func1<T: MyTrait>(x: T) { /* ... */ }
fn my_func1(x: impl MyTrait) { /* ... */ }


fn my_func2<T: MyTrait>() -> T { /* ... */ }
fn my_func2()  -> impl MyTrait { /* ... */ }
```

- when `impl` appears multiple times it they are potentially different each time

```rust
// 1) Same type
fn same_type<T: MyTrait>(x: T, y: T) { /* ... */ }

// 2) Potentially different types
fn maybe_diff<T: MyTrait, U: MyTrait>(x: T, y: U) { /* ... */ }

// 3) impl version ≈ (2)
fn impl_version(x: impl MyTrait, y: impl MyTrait) { /* ... */ }
```

- in the following example the compiler rejects the second because the return type would be undefined because it don't have to be equivalent like in the first case

```rust
fn my_func3<T: MyTrait>(x: T)  -> T { /* ... */ }
fn my_func3(x: impl MyTrait) -> impl MyTrait { /* ... */ }
// ❌ rejected
```

- `impl Trait` in return position must be the **outermost** type thus the following doesn't work

```rust
fn foo() -> Vec<impl MyTrait> { /* ... */ }
// ❌ rejected
fn foo<T: MyTrait>() -> Vec<T> { /* ... */ }
//works
```
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

Tags: code rust
<!--ID: 1756383003753-->
END




START
Basic
What does this mean?

```rust
fn my_funct<T: std::ops::Add<Output = T>, U: std::ops::Add<Output = U>>(x: T, y: T, u: U, v: U) -> (T, U) {...}
```

Back: 

- this means `T: std::ops::Add<Output = T>` the input [[r data type]] has to implement the `Add` [[r trait]] and `T` is the [[r data type]] of the output of the add operation

```rust
fn add_all<T: std::ops::Add<Output = T>, U: std::ops::Add<Output = U>>(x: T, y: T, u: U, v: U) -> (T, U) {
    (x + y, u + v)
}
```

## generic type
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
<!--ID: 1756383003756-->
END