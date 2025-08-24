### closure
- anonymous [[r function]] like a [[py lambda functions]] in [[python]]

```rust
fn apply_to_vec<F>(v: Vec<i32>, f: F) -> Vec<i32>
where
    F: Fn(i32) -> i32,
{
    v.into_iter().map(f).collect()
}

fn main() {
    let v = vec![1, 2, 3];
    let squared = apply_to_vec(v, |x| x * x); // closure
    println!("{:?}", squared); // [1, 4, 9]
}
```