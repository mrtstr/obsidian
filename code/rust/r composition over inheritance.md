### composition over inheritance
- **Inheritance**: build new types by extending existing ones
	→ Often leads to rigid hierarchies and the _fragile base class problem_ 
- **Composition**: build types by combining smaller, reusable components.
	→ Leads to more flexible and decoupled code. 
#### example
inheritance design:

```python
class Animal:
    def __init__(self, name: str):
        self.name = name
    def eat(self):
        print(f"{self.name} is eating")

class Dog(Animal):
    def bark(self):
        print(f"{self.name}: Bark!")

d = Dog("Rex")
d.eat()     # inherited
d.bark()    # Dog-specific
```

composition design in [[python]]:
```python
class Animal:
    def __init__(self, name: str):
        self.name = name
    def eat(self):
        print(f"{self.name} is eating")

class Dog:
    def __init__(self, name: str):
        self.animal = Animal(name)  # Dog HAS an Animal
    def bark(self):
        print(f"{self.animal.name}: Bark!")
    def eat(self):
        self.animal.eat()           # delegate

d = Dog("Rex")
d.eat()
d.bark()
```

composition design in [[rust]]:

```rust
trait Animal { fn name(&self) -> &str; }
trait Eater { fn eat(&self); }

struct Dog { name: String }
struct Cat { name: String }

impl Animal for Dog { fn name(&self) -> &str { &self.name } }
impl Animal for Cat { fn name(&self) -> &str { &self.name } }

// implmentent a trait for a trait
impl<T: Animal> Eater for T {
    fn eat(&self) { println!("{}: eats", self.name()); }
}

fn main() {
    let d = Dog { name: "Rex".into() };
    let c = Cat { name: "Misty".into() };

    d.eat();
    c.eat();

    // trait objects also work (Eater is object-safe)
    let zoo: Vec<&dyn Eater> = vec![&d, &c];
    for a in zoo { a.eat(); }
}
```


# anki

START
Basic
- explain the OO design approach of [[rust]]
- implement the following example in [[rust]]

```python
class Animal:
    def __init__(self, name: str):
        self.name = name
    def eat(self):
        print(f"{self.name} is eating")

class Dog(Animal):
    def bark(self):
        print(f"{self.name}: Bark!")

d = Dog("Rex")
d.eat()     # inherited
d.bark()    # Dog-specific
```

Back: 
### composition over inheritance
- **Inheritance**: build new types by extending existing ones
	→ Often leads to rigid hierarchies and the _fragile base class problem_ 
- **Composition**: build types by combining smaller, reusable components.
	→ Leads to more flexible and decoupled code. 
#### example
inheritance design:

```python
class Animal:
    def __init__(self, name: str):
        self.name = name
    def eat(self):
        print(f"{self.name} is eating")

class Dog(Animal):
    def bark(self):
        print(f"{self.name}: Bark!")

d = Dog("Rex")
d.eat()     # inherited
d.bark()    # Dog-specific
```

composition design in [[python]]:

```python
class Animal:
    def __init__(self, name: str):
        self.name = name
    def eat(self):
        print(f"{self.name} is eating")

class Dog:
    def __init__(self, name: str):
        self.animal = Animal(name)  # Dog HAS an Animal
    def bark(self):
        print(f"{self.animal.name}: Bark!")
    def eat(self):
        self.animal.eat()           # delegate

d = Dog("Rex")
d.eat()
d.bark()
```

composition design in [[rust]]:

```rust
trait Animal { fn name(&self) -> &str; }
trait Eater { fn eat(&self); }

struct Dog { name: String }
struct Cat { name: String }

impl Animal for Dog { fn name(&self) -> &str { &self.name } }
impl Animal for Cat { fn name(&self) -> &str { &self.name } }

// implmentent a trait for a trait
impl<T: Animal> Eater for T {
    fn eat(&self) { println!("{}: eats", self.name()); }
}

fn main() {
    let d = Dog { name: "Rex".into() };
    let c = Cat { name: "Misty".into() };

    d.eat();
    c.eat();

    // trait objects also work (Eater is object-safe)
    let zoo: Vec<&dyn Eater> = vec![&d, &c];
    for a in zoo { a.eat(); }
}
```

Tags: code rust
<!--ID: 1759081496655-->
END