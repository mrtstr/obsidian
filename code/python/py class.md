# [[py class]]
## [[py class]] definition
 - blueprints for creating [[py object]] that are defined by 3 properties
	1) the name of the [[py class]] (`__name__`)
	2) the paraent [[py class]] (`__base__`) if not given they [[py inheritance|inherent]] from [[py type]]
	3) its attributes: methods and data (`__dict__`)
 - [[py class|classes]] are [[py object]] themselves from the 'base class' [[py type]]

![[py object creation#py object creation]]


classes are themselves instances of a "metaclass" - and the default metaclass is `type`
All classes in Python also inherit from `object` - and that includes `type`.
The class `object` itself must also be an instance of `type`


## [[py dunder valiables]] [[py class]]
- `__name__`: stores the name of the [[py class]]
-   `__module__`: stores the name of the [[py module]] they were defined in within
-   `__bases__`: stores their base classes
- -   `__mro__`: stores their method resolution order (see [[py inheritance]])
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
 - blueprints for creating [[py object]]
 - [[py class|classes]] are [[py object]] themselves from the 'base class' type

### [[py object creation]]
#### [[py object creation]] [[py dunder method]]
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

![[class-chain 2.webp]]

## [[py dunder valiables]] [[py class]]
- `__name__`: stores the name of the [[py class]]
-   `__module__`: stores the name of the [[py module]] they were defined in within
-   `__bases__`: stores their base classes
- -   `__mro__`: stores their method resolution order (see [[py inheritance]])

#### [[py dunder valiables]] [[py object]]
-   `__class__`: stores the [[py class]] of the [[py object]] 
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

## [[py dunder valiables]] [[py class]]
- `__name__`: stores the name of the [[py class]]
-   `__module__`: stores the name of the [[py module]] they were defined in within
-   `__bases__`: stores their base classes
- -   `__mro__`: stores their method resolution order (see [[py inheritance]])

#### [[py dunder valiables]] [[py object]]
-   `__class__`: stores the [[py class]] of the [[py object]] 
-   `__dict__`: stores the attributes of the [[py object]]
Tags: code python
<!--ID: 1698748522706-->
END