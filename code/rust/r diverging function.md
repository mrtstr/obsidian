### diverging function
- a [[r diverging function]] in [[rust]] is a [[r function]] that never return
- for example it might end the control flow or loop forever
- this is annotated like the following

```rust
fn forever() -> ! {
    loop {}
}

fn crash() -> ! {
    panic!("something went wrong");
}
```


START
Basic
[[r diverging function]]
- concept
- syntax

Back: 
### diverging function
- a [[r diverging function]] in [[rust]] is a [[r function]] that never return
- for example it might end the control flow or loop forever
- this is annotated like the following

```rust
fn forever() -> ! {
    loop {}
}

fn crash() -> ! {
    panic!("something went wrong");
}
```
Tags: code rust
<!--ID: 1759683035808-->
END