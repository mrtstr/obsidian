# [[py class]]
## [[py class]] definition
 - blueprints for creating [[py object]] that are defined by 3 properties
	1) the name of the [[py class]] (`__name__`)
	2) the paraent [[py class]] (`__bases__`) if not given they [[py inheritance|inherent]] from the [[py base object]] 
	3) its attributes: methods and data (`__dict__`)
 - [[py class|classes]] are [[py object]] themselves instancianted from the metaclass [[py type]] based on its 3 properties

![[py object creation#py object creation py dunder method]]


## [[py dunder valiables]] [[py class]]
- `__name__`: stores the name of the [[py class]]
-   `__module__`: stores the name of the [[py module]] they were defined in within
-   `__bases__`: stores their (direct) parent classes ([[py base object]] of no other parent)
- -   `__mro__`: stores their method resolution order (see [[py inheritance]]) from the class to the [[py base object]] `(<class itself>, <optional parent classes ...>, <object>)`
![[py object#py dunder valiables py object]]

## example [[py dunder method]] or [[py class]]
```
MutableContainer.__class__=<class 'type'>

MutableContainer.__dict__=
{
	'__module__': 'test_package.test_subpackage.module_sub', 
	'__init__': <function MutableContainer.__init__ at 0x7fdd8573e3b0>, 
	'__setitem__': <function MutableContainer.__setitem__ at 0x7fdd8573e440>, 
	'__delitem__': <function MutableContainer.__delitem__ at 0x7fdd8573e4d0>, 
	'__doc__': None
}

MutableContainer.__name__='MutableContainer'

MutableContainer.__module__ = 'test_package.test_subpackage.module_sub'
MutableContainer.__bases__=(
	<class 'test_package.test_subpackage.module_sub.BaseContainer'>,
)
MutableContainer.__mro__=(
	<class 'test_package.test_subpackage.module_sub.MutableContainer'>,
	<class 'test_package.test_subpackage.module_sub.BaseContainer'>, 
	<class 'object'>
)
```

```python
print(my_container.__class__.__class__)
# <class 'type'>
print(my_container.__class__)
# <class 'test_package.test_subpackage.module_sub.MutableContainer'>
print(MutableContainer.__bases__)
# (<class 'test_package.test_subpackage.module_sub.BaseContainer'>,)
print(MutableContainer.__bases__(0).__bases__)
# (<class 'object'>,)
print(MutableContainer.__bases__(0).__bases__(0).__bases__(0))
# None
```

![[py container objects#example mutable py container objects]]

# anki

START
Basic
[[py class]]
- defintion (2)
- relationship to [[py type]]
- [[py dunder valiables]] (6)
Back: 
## [[py class]] definition
 - blueprints for creating [[py object]] that are defined by 3 properties
	1) the name of the [[py class]] (`__name__`)
	2) the paraent [[py class|classes]] (`__bases__`) if not given they [[py inheritance|inherent]] from the [[py base object]] 
	3) its attributes: methods and data (`__dict__`)
 - [[py class|classes]] are [[py object]] themselves instancianted from the metaclass [[py type]] based on its 3 properties


#### [[py dunder method]]
#### `__new__(cls, ...)`
- first method called in [[py object creation]]
- recives a reference to the [[py class]] (`cls`) plus all the arguments passed during the object creation call
#### `__init__(self, ...)`
- first method that is called after the [[py object]] is instanciated 
- recives a reference to the instance ([[py object]]) itself (`self`) plus all the arguments passed during the object creation call
#### `__del__(self)`
- destructor that is called when object is deleted 

### [[py type]]
- [[py type]] of an [[py object]] are the [[py class]] it was created from (`type(obj) == obj.__class__`)
- [[py class]] and [[py type]] are the same concept
- `type` is the name of the base [[py class]] every [[py class]] [[py inheritance]] from even itself

![[class-chain 4.webp]]

## [[py dunder valiables]] [[py class]]
- `__name__`: stores the name of the [[py class]]
-   `__module__`: stores the name of the [[py module]] they were defined in within
-   `__bases__`: stores their (direct) parent classes ([[py base object]] of no other parent)
- -   `__mro__`: stores their method resolution order (see [[py inheritance]]) from the class to the [[py base object]] `(<class itself>, <optional parent classes ...>, <object>)`

#### [[py dunder valiables]] [[py object]]
-   `__class__`: stores the [[py class]] of the [[py object]] (metaclass [[py type]] if it's a [[py class]] itself)
-   `__dict__`: stores the attributes of the [[py object]]
Tags: code python
<!--ID: 1698748522703-->
END


START

Basic
[[py dunder valiables]] of the following [[py class]] (6)

```python
class MutableContainer(BaseContainer):
	def __init__(self, *args):
		super().__init__(*args) # initilize the base container
		# convert tuple of base class to list to make it mutable
		self.values = list(self.values)
	
	def __setitem__(self, nkey, value):
		print(f"The __setitem__ method was called")
		nkey = int(nkey)
		if nkey < len(self) and nkey >= 0:
			print(f"setting {value} to nkey {nkey}")
			self.values[nkey] = value
			print(self.values)
		else:
			raise TypeError(f"index {nkey} out of bound")
	
	def __delitem__(self, nkey):
		print(f"The __delitem__ method was called")
		nkey = int(nkey)
		if nkey < len(self) and nkey >= 0:
			print(f"removing {self.values[nkey]}")
			del self.values[nkey]
			print(self.values)
		else:
			raise TypeError(f"index {nkey} out of bound")

```

```python
print(my_container.__class__.__class__)

print(my_container.__class__)

print(MutableContainer.__bases__)

print(MutableContainer.__bases__(0).__bases__)

print(MutableContainer.__bases__(0).__bases__(0).__bases__(0))

```

Back: 

```
MutableContainer.__class__=<class 'type'>

MutableContainer.__dict__=
{
	'__module__': 'test_package.test_subpackage.module_sub', 
	'__init__': <function MutableContainer.__init__ at 0x7fdd8573e3b0>, 
	'__setitem__': <function MutableContainer.__setitem__ at 0x7fdd8573e440>, 
	'__delitem__': <function MutableContainer.__delitem__ at 0x7fdd8573e4d0>, 
	'__doc__': None
}

MutableContainer.__name__='MutableContainer'

MutableContainer.__module__ = 'test_package.test_subpackage.module_sub'
MutableContainer.__bases__=(
	<class 'test_package.test_subpackage.module_sub.BaseContainer'>,
)
MutableContainer.__mro__=(
	<class 'test_package.test_subpackage.module_sub.MutableContainer'>,
	<class 'test_package.test_subpackage.module_sub.BaseContainer'>, 
	<class 'object'>
)
```

```python
print(my_container.__class__.__class__)
# <class 'type'>
print(my_container.__class__)
# <class 'test_package.test_subpackage.module_sub.MutableContainer'>
print(MutableContainer.__bases__)
# (<class 'test_package.test_subpackage.module_sub.BaseContainer'>,)
print(MutableContainer.__bases__(0).__bases__)
# <class 'object'>
print(MutableContainer.__bases__(0).__bases__(0).__bases__(0))
# None
```

## [[py dunder valiables]] [[py class]]
- `__name__`: stores the name of the [[py class]]
-   `__module__`: stores the name of the [[py module]] they were defined in within
-   `__bases__`: stores their (direct) parent classes ([[py base object]] of no other parent)
- -   `__mro__`: stores their method resolution order (see [[py inheritance]]) from the class to the [[py base object]] `(<class itself>, <optional parent classes ...>, <object>)`

#### [[py dunder valiables]] [[py object]]
-   `__class__`: stores the [[py class]] of the [[py object]] (metaclass [[py type]] if it's a [[py class]] itself)
-   `__dict__`: stores the attributes of the [[py object]]
Tags: code python
<!--ID: 1698748522706-->
END


START

Basic
[[py dunder valiables]] of the following [[py class]] (6)

```python
class MutableContainer(BaseContainer):
	def __init__(self, *args):
		super().__init__(*args) # initilize the base container
		# convert tuple of base class to list to make it mutable
		self.values = list(self.values)
	
	def __setitem__(self, nkey, value):
		print(f"The __setitem__ method was called")
		nkey = int(nkey)
		if nkey < len(self) and nkey >= 0:
			print(f"setting {value} to nkey {nkey}")
			self.values[nkey] = value
			print(self.values)
		else:
			raise TypeError(f"index {nkey} out of bound")
	
	def __delitem__(self, nkey):
		print(f"The __delitem__ method was called")
		nkey = int(nkey)
		if nkey < len(self) and nkey >= 0:
			print(f"removing {self.values[nkey]}")
			del self.values[nkey]
			print(self.values)
		else:
			raise TypeError(f"index {nkey} out of bound")

```

```python
print(my_container.__class__.__class__)

print(my_container.__class__.__class__.__class__)

print(my_container.__class__)

print(my_container.__class__.__bases__)

print(MutableContainer.__bases__)

print(MutableContainer.__bases__(0).__bases__)

print(MutableContainer.__bases__(0).__bases__(0).__bases__)

```

Back: 
```python
print(my_container.__class__.__class__)
# <class 'type'>
print(my_container.__class__.__class__.__class__)
# <class 'type'>
print(my_container.__class__)
# <class 'test_package.test_subpackage.module_sub.MutableContainer'>
print(my_container.__class__.__bases__)
# (<class 'test_package.test_subpackage.module_sub.BaseContainer'>,)
print(MutableContainer.__bases__)
# (<class 'test_package.test_subpackage.module_sub.BaseContainer'>)
print(MutableContainer.__bases__(0).__bases__)
# (<class 'object'>,)
print(MutableContainer.__bases__(0).__bases__(0).__bases__)
# None
```

## [[py dunder valiables]] [[py class]]
- `__name__`: stores the name of the [[py class]]
-   `__module__`: stores the name of the [[py module]] they were defined in within
-   `__bases__`: stores their (direct) parent classes ([[py base object]] of no other parent)
- -   `__mro__`: stores their method resolution order (see [[py inheritance]]) from the class to the [[py base object]] `(<class itself>, <optional parent classes ...>, <object>)`

#### [[py dunder valiables]] [[py object]]
-   `__class__`: stores the [[py class]] of the [[py object]] (metaclass [[py type]] if it's a [[py class]] itself)
-   `__dict__`: stores the attributes of the [[py object]]
Tags: code python
<!--ID: 1698764482219-->
END