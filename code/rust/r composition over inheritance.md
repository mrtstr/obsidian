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
trait Eater { fn eat(&self); }

struct Dog;
struct Cat;

impl Eater for Dog { fn eat(&self) { println!("Dog eats kibble"); } }
impl Eater for Cat { fn eat(&self) { println!("Cat eats fish"); } }

fn feed<T: Eater>(a: T) { a.eat(); }
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
trait Eater { fn eat(&self); }

struct Dog;
struct Cat;

impl Eater for Dog { fn eat(&self) { println!("Dog eats kibble"); } }
impl Eater for Cat { fn eat(&self) { println!("Cat eats fish"); } }

fn feed<T: Eater>(a: T) { a.eat(); }
```

Tags: code rust
<!--ID: 1759081496655-->
END