# [[py type]]
`type()` is a [[py buidin functions]] that is 
1) the base [[py class]] of every [[py class]] and is used for the creation of [[py object]] and can be used for creating meta [[py class]]
2) return the [[py class]] a pased [[py object]] was created from (`type(obj) == obj.__class__`)

![[class-chain 1.webp]]

## [[py type]] for creating meta [[py class]]
- `type` can be used for ceating classes by providing 
	1) the `__name__` of the new [[py class]]
	2) the `__base__` (parent [[py class]])
	3) the `__dict__` containing all attributes (functions and data)
- `type` will return the [[py class]]
```python
def __init__(self, val):
	self.atr2 = val
	print("__init__() wal called")

Foo = type(
	'Foo', # __name__ of class
	(), # __base__ of class (in this case its type)
	{
		"atr":99,
		"say_hi": lambda x: print("Hi!"),
		"__init__": __init__,
	} # __dict__of class
)

foo = Foo(77)
foo.say_hi()
print(foo.atr)
print(foo.atr2)
```

## [[py type]] for returning the [[py class]] of an [[py object]]
- when a [[py object]] is passed to `type(obj)` it will return [[py object]] [[py dunder valiables]] `obj.__class__` containing the [[py class]] if was created from

# anki

START
Basic
- concept of a [[py type]]
- two ways `type()` can be used
Back: 
# [[py type]]
`type()` is a [[py buidin functions]] that is 
1) the base [[py class]] of every [[py class]] and is used for the creation of [[py object]] and can be used for creating meta [[py class]]
2) return the [[py class]] a pased [[py object]] was created from (`type(obj) == obj.__class__`)

![[class-chain 1.webp]]

## [[py type]] for creating meta [[py class]]
- `type` can be used for ceating classes by providing 
	1) the `__name__` of the new [[py class]]
	2) the `__base__` (parent [[py class]])
	3) the `__dict__` containing all attributes (functions and data)
- `type` will return the [[py class]]
```python
def __init__(self, val):
	self.atr2 = val
	print("__init__() wal called")

Foo = type(
	'Foo', # __name__ of class
	(), # __base__ of class (in this case its type)
	{
		"atr":99,
		"say_hi": lambda x: print("Hi!"),
		"__init__": __init__,
	} # __dict__of class
)

foo = Foo(77)
foo.say_hi()
print(foo.atr)
print(foo.atr2)
```

## [[py type]] for returning the [[py class]] of an [[py object]]
- when a [[py object]] is passed to `type(obj)` it will return [[py object]] [[py dunder valiables]] `obj.__class__` containing the [[py class]] if was created from

Tags: code python
<!--ID: 1698748522682-->
END


# anki

START
Basic
- create a meta [[py class]] named `Foo`, that has an atribute 99 and a `__init__` function printing that it was called 
Back: 

## [[py type]] for creating meta [[py class]]
- `type` can be used for ceating classes by providing 
	1) the `__name__` of the new [[py class]]
	2) the `__base__` (parent [[py class]])
	3) the `__dict__` containing all attributes (functions and data)
- `type` will return the [[py class]]
```python
def __init__(self, val):
	self.atr2 = val
	print("__init__() wal called")

Foo = type(
	'Foo', # __name__ of class
	(), # __base__ of class (in this case its type)
	{
		"atr":99,
		"say_hi": lambda x: print("Hi!"),
		"__init__": __init__,
	} # __dict__of class
)

foo = Foo(77)
foo.say_hi()
print(foo.atr)
print(foo.atr2)
```

Tags: code python
<!--ID: 1698748522689-->
END