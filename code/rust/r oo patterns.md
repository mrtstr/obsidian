## oo patterns
- [[r enum]] based
```rust
struct Dog {
    name: String,
}

struct Cat {
    name: String,
}

enum Animal {
    Cat(Cat),
    Dog(Dog),
}

trait Eater {
    fn eat(&self);
}

impl Eater for Animal {
    fn eat(&self) {
        let name = match self {
            Animal::Cat(c) => &c.name,
            Animal::Dog(d) => &d.name,
        };
        println!("{} is eating!", name);
    }
}
```

#### **Trait Objects (Dynamic Dispatch)**

```rust
trait Eater {
    fn eat(&self);
    fn name(&self) -> &str;
}

struct Dog {
    name: String,
}

impl Eater for Dog {
    fn eat(&self) {
        println!("{} (dog) is eating!", self.name);
    }
    
    fn name(&self) -> &str {
        &self.name
    }
}

struct Cat {
    name: String,
}

impl Eater for Cat {
    fn eat(&self) {
        println!("{} (cat) is eating!", self.name);
    }
    
    fn name(&self) -> &str {
        &self.name
    }
}

// Usage with trait objects (dynamic dispatch)
fn feed_animal(animal: &dyn Eater) {
    animal.eat();
}

fn main() {
    let dog = Dog { name: String::from("Buddy") };
    let cat = Cat { name: String::from("Whiskers") };
    
    let animals: Vec<&dyn Eater> = vec![&dog, &cat];
    
    for animal in animals {
        animal.eat();
    }
}
```


```rust
trait Eater {
    fn eat(&self);
    fn name(&self) -> &str;
}

struct Dog {
    name: String,
}

impl Eater for Dog {
    fn eat(&self) {
        println!("{} (dog) is eating!", self.name);
    }
    fn name(&self) -> &str {
        &self.name
    }
}

struct Cat {
    name: String,
}

impl Eater for Cat {
    fn eat(&self) {
        println!("{} (cat) is eating!", self.name);
    }
    fn name(&self) -> &str {
        &self.name
    }
}

// Generic function (static dispatch - monomorphization)
fn feed_animal<T: Eater>(animal: &T) {
    animal.eat();
}

fn main() {
    let dog = Dog { name: String::from("Buddy") };
    let cat = Cat { name: String::from("Whiskers") };
    
    feed_animal(&dog);  // Compiler generates feed_animal::<Dog>
    feed_animal(&cat);  // Compiler generates feed_animal::<Cat>
}
```


## **Comparison Table**

|Feature|Dynamic Dispatch (`dyn Trait`)|Generics (`<T: Trait>`)|
|---|---|---|
|**Type known at**|Runtime|Compile time|
|**Method call**|Vtable lookup (indirect)|Direct call (inlined)|
|**Performance**|Small overhead (~1-2 cycles)|Zero overhead|
|**Code size**|Smaller binary|Larger binary (code duplication)|
|**Heterogeneous collections**|✅ `Vec<Box<dyn Trait>>`|❌ Can't mix types|
|**Compile time**|Faster|Slower (more codegen)|
|**When to use**|Mixed types, plugins|Known types, performance critical|
## **Memory Layout**

### **Dynamic Dispatch (Fat Pointer)**

```
┌─────────────┐
│  &dyn Trait │  (16 bytes on 64-bit)
├─────────────┤
│ data ptr    │ ──→ actual object
│ vtable ptr  │ ──→ method pointers
└─────────────┘

Vtable:
┌──────────────┐
│ drop fn      │
│ size         │
│ align        │
│ speak()      │ ──→ Dog::speak or Cat::speak
└──────────────┘
```

### **Generics (Regular Pointer)**

```
┌──────────┐
│  &T      │  (8 bytes on 64-bit)
├──────────┤
│ data ptr │ ──→ actual object
└──────────┘

No vtable - compiler knows exact type!
```

## **Practical Examples**

### **Use Dynamic Dispatch When:**

```rust
struct Zoo {
    animals: Vec<Box<dyn Animal>>,  // Mix different animals
}

// 3. Trait objects as return types
fn create_animal(name: &str) -> Box<dyn Animal> {
    match name {
        "dog" => Box::new(Dog),
        "cat" => Box::new(Cat),
        _ => panic!("Unknown animal"),
    }
}
```

### **Use Generics When:**

```rust
// 1. Performance critical code
fn sort_slice<T: Ord>(slice: &mut [T]) {  // Zero-cost abstraction
    slice.sort();  // Compiler optimizes for specific T
}

// 2. Known types at compile time
fn process_numbers<T: Add<Output = T>>(a: T, b: T) -> T {
    a + b  // Inlined, no overhead
}

// 3. Iterator chains (heavily optimized)
fn sum_evens<I>(iter: I) -> i32 
where 
    I: Iterator<Item = i32>,
{
    iter.filter(|x| x % 2 == 0).sum()  // All inlined
}
```