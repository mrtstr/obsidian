
## [[py inheritance]] 

### [[py inheritance]] process
- When a [[py object]] is [[py object creation|instantiated]] its inherentence tree is searched, and the **method resolution order** is determined
-  inherentence tree is genereated by interating threw the base [[py class|classes]] ([[py dunder valiables]] `__bases__`)
- the [[py object]] inherents all attributes (what is in `__dict__`) from all ancestors but the nearest [[py class]] in the `mro` overwrites


### [[py inheritance]] example
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

`Bar.__mro__ = (__main__.Bar, __main__.Foo, object)`

### [[py inheritance]] `super()`
- Return a proxy object that delegates method calls to the next [[py class]] in the `mro`
- This is useful for accessing inherited methods that have been overridden in a class.



# anki

START

Basic
- how does [[py inheritance]] work
- how does `super()` do?
- what is the `mro`?
- give the `mro` for the following example

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

## [[py inheritance]] 

### [[py inheritance]] process
- When a [[py object]] is [[py object creation|instantiated]] its inherentence tree is searched, and the **method resolution order** is determined
-  inherentence tree is genereated by interating threw the base [[py class|classes]] ([[py dunder valiables]] `__bases__`)
- the [[py object]] inherents all attributes (what is in `__dict__`) from all ancestors but the nearest [[py class]] in the `mro` overwrites


### [[py inheritance]] example
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

`Bar.__mro__ = (__main__.Bar, __main__.Foo, object)`

### [[py inheritance]] `super()`
- Return a proxy object that delegates method calls to the next [[py class]] in the `mro`
- This is useful for accessing inherited methods that have been overridden in a class.

Tags: code python
<!--ID: 1698764482205-->
END