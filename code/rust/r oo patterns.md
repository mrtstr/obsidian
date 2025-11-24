## oo patterns
- we have the following structs, and we want to implement eater for both and keep multiple eaters (`Cat` and `Dog`) in a [[r vec]] and call eat of both
1) wrap then in an [[r enum]] and implement the [[r trait]] once for the [[r enum]] but check the type in the implementation
2) implement it seperatly for each [[r struct]] and wrap the structs in a [[r box]] because the size of not known at [[r compile time]]


```rust
struct Dog {
    name: String,
}

struct Cat {
    name: String,
}

trait Eater {
    fn eat(&self);
    fn name(&self) -> &str;
}
```


- Use the **enum pattern** when you have a **closed set of types** and you control them all.
- Use **trait objects** when the set of types should be **open/extendable**, or when you’re writing a library others will extend.
#### enums

```rust
enum Animal {
    Cat(Cat),
    Dog(Dog),
}

impl Eater for Animal {
    fn name(&self) -> &str {
        match self {
            Animal::Cat(c) => &c.name,
            Animal::Dog(d) => &d.name, 
        }
    }
    
    fn eat(&self) {
        println!("{} is eating!", self.name());
    }
}

let animals: Vec<Animal> = vec![
	Animal::Dog(Dog { name: "Buddy".to_string() }),
	Animal::Cat(Cat { name: "Whiskers".to_string() })
];

for animal in animals {
	animal.eat();
}

```


#### trait objects

```rust

impl Eater for Dog {
    fn eat(&self) {
        println!("{} (dog) is eating!", self.name);
    }
    fn name(&self) -> &str {
        &self.name
    }
}


impl Eater for Cat {
    fn eat(&self) {
        println!("{} (cat) is eating!", self.name);
    }
    
    fn name(&self) -> &str {
        &self.name
    }
}
let animals: Vec<Box<dyn Eater>> = vec![
	Box::new(Dog { name: "Buddy".to_string() }),
	Box::new(Cat { name: "Whiskers".to_string() })
];

for animal in animals {
	animal.eat();
}
```



# anki

START
Basic

- we have the following structs, and we want to implement eater for both and keep multiple eaters (`Cat` and `Dog`) in a [[r vec]] and call eat of both

```rust
struct Dog {
    name: String,
}

struct Cat {
    name: String,
}

trait Eater {
    fn eat(&self);
    fn name(&self) -> &str;
}
```

Back: 

1) wrap then in an [[r enum]] and implement the [[r trait]] once for the [[r enum]] but check the type in the implementation
2) implement it seperatly for each [[r struct]] and wrap the structs in a [[r box]] because the size of not known at [[r compile time]]

- Use the **enum pattern** when you have a **closed set of types** and you control them all.
- Use **trait objects** when the set of types should be **open/extendable**, or when you’re writing a library others will extend.

#### enums

```rust
enum Animal {
    Cat(Cat),
    Dog(Dog),
}

impl Eater for Animal {
    fn name(&self) -> &str {
        match self {
            Animal::Cat(c) => &c.name,
            Animal::Dog(d) => &d.name, 
        }
    }
    
    fn eat(&self) {
        println!("{} is eating!", self.name());
    }
}

let animals: Vec<Animal> = vec![
	Animal::Dog(Dog { name: "Buddy".to_string() }),
	Animal::Cat(Cat { name: "Whiskers".to_string() })
];

for animal in animals {
	animal.eat();
}

```


#### trait objects

```rust

impl Eater for Dog {
    fn eat(&self) {
        println!("{} (dog) is eating!", self.name);
    }
    fn name(&self) -> &str {
        &self.name
    }
}


impl Eater for Cat {
    fn eat(&self) {
        println!("{} (cat) is eating!", self.name);
    }
    
    fn name(&self) -> &str {
        &self.name
    }
}
let animals: Vec<Box<dyn Eater>> = vec![
	Box::new(Dog { name: "Buddy".to_string() }),
	Box::new(Cat { name: "Whiskers".to_string() })
];

for animal in animals {
	animal.eat();
}
```
Tags: code rust
<!--ID: 1763982709983-->
END
