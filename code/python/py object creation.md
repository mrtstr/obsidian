## [[py object creation]]
### [[py object creation]] process
When a [[py class]] is instanciated, the [[py interpreter]] will call 
1) the antsertery for the first `__new__` [[py dunder method]] defined and will pass the [[py class]] itself togather with the arguments to it `__new__(cls, <args>)`
2) the antsertery for the first `__int__` [[py dunder method]] defined and will pass the new created [[py object]] togather with the arguments to it `__new__(self, <args>)`
- if no `__new__` or `__init__` method is defined, it will call the `__new__` or `__new__` method of the [[py base object]] 

### [[py object creation]] [[py dunder method]]
#### `__new__(cls, ...)`
- first method called in [[py object creation]]
- recives a reference to the [[py class]] (`cls`) plus all the arguments passed during the object creation call
#### `__init__(self, ...)`
- first method that is called after the [[py object]] is instanciated 
- recives a reference to the instance ([[py object]]) itself (`self`) plus all the arguments passed during the object creation call
#### `__del__(self)`
- destructor that is called when object is deleted 

### [[py object creation]] example
- in the given example the `__new__` method of `Foo` is called because `Bar` [[py inheritance|inherented]] its `__new__` method from `Fo` since it doesn't have its ows
- since `Bar` has its ows `__init__` method it does not inherent it

![[py inheritance#py inheritance example]]


```python
bar1 = Bar(44)
# __new__Foooooo 44 
# __init__Barrrrrr 44

##  equivalent to

bar_raw = Foo.__new__(Bar, 44) # Bar inherited __new__ from Fo
# __new__Foooooo 44 
bar2 = Bar.__init__(bar_raw, 44) # Bar inherited nothing from Fo
# __init__Barrrrrr 44
```

# Anki
START
Basic
[[py object creation]]
- process and involved methods

Back: 
## [[py object creation]]
### [[py object creation]] process
When a [[py class]] is instanciated, the [[py interpreter]] will call 
1) the antsertery for the first `__new__` [[py dunder method]] defined and will pass the [[py class]] itself togather with the arguments to it `__new__(cls, <args>)`
2) the antsertery for the first `__int__` [[py dunder method]] defined and will pass the new created [[py object]] togather with the arguments to it `__new__(self, <args>)`
- if no `__new__` or `__init__` method is defined, it will call the `__new__` or `__new__` method of the [[py base object]] 

### [[py object creation]] [[py dunder method]]
#### `__new__(cls, ...)`
- first method called in [[py object creation]]
- recives a reference to the [[py class]] (`cls`) plus all the arguments passed during the object creation call
#### `__init__(self, ...)`
- first method that is called after the [[py object]] is instanciated 
- recives a reference to the instance ([[py object]]) itself (`self`) plus all the arguments passed during the object creation call
#### `__del__(self)`
- destructor that is called when object is deleted 

### [[py object creation]] example
- in the given example the `__new__` method of `Foo` is called because `Bar` [[py inheritance|inherented]] its `__new__` method from `Fo` since it doesn't have its ows
- since `Bar` has its ows `__init__` method it does not inherent it

```python
class Foo:
	def __new__(cls, val):
		print(f"__new__Foooooo {val}")
		x = object.__new__(cls)
		return x
	
	def __init__(self, val) -> None:
		print(f"__init__Foooooo {val}")

class Bar(Foo):
	def __init__(self, val) -> None:
		print(f"__init__Barrrrrr {val}")
```


```python
bar1 = Bar(44)
# __new__Foooooo 44 
# __init__Barrrrrr 44

##  equivalent to

bar_raw = Foo.__new__(Bar, 44) # Bar inherited __new__ from Fo
# __new__Foooooo 44 
bar2 = Bar.__init__(bar_raw, 44) # Bar inherited nothing from Fo
# __init__Barrrrrr 44
```

Tags: code python
<!--ID: 1698764482210-->
END

START
Basic
[[py object creation]]
- what happens in the given example and why

```python
class Foo:
	def __new__(cls, val):
		print(f"__new__Foooooo {val}")
		x = object.__new__(cls)
		return x
	
	def __init__(self, val) -> None:
		print(f"__init__Foooooo {val}")

class Bar(Foo):
	def __init__(self, val) -> None:
		print(f"__init__Barrrrrr {val}")

bar1 = Bar(44)
```

Back: 

### [[py object creation]] example
- in the given example the `__new__` method of `Foo` is called because `Bar` [[py inheritance|inherented]] its `__new__` method from `Fo` since it doesn't have its ows
- since `Bar` has its ows `__init__` method it does not inherent it
```python
bar1 = Bar(44)
# __new__Foooooo 44 
# __init__Barrrrrr 44

##  equivalent to

bar_raw = Foo.__new__(Bar, 44) # Bar inherited __new__ from Fo
# __new__Foooooo 44 
bar2 = Bar.__init__(bar_raw, 44) # Bar inherited nothing from Fo
# __init__Barrrrrr 44
```

## [[py object creation]]
### [[py object creation]] process
When a [[py class]] is instanciated, the [[py interpreter]] will call 
1) the antsertery for the first `__new__` [[py dunder method]] defined and will pass the [[py class]] itself togather with the arguments to it `__new__(cls, <args>)`
2) the antsertery for the first `__int__` [[py dunder method]] defined and will pass the new created [[py object]] togather with the arguments to it `__new__(self, <args>)`
- if no `__new__` or `__init__` method is defined, it will call the `__new__` or `__new__` method of the [[py base object]] 

### [[py object creation]] [[py dunder method]]
#### `__new__(cls, ...)`
- first method called in [[py object creation]]
- recives a reference to the [[py class]] (`cls`) plus all the arguments passed during the object creation call
#### `__init__(self, ...)`
- first method that is called after the [[py object]] is instanciated 
- recives a reference to the instance ([[py object]]) itself (`self`) plus all the arguments passed during the object creation call
#### `__del__(self)`
- destructor that is called when object is deleted 

Tags: code python
<!--ID: 1698764482213-->
END