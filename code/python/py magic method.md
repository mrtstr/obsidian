## [[python]] [[py magic method]] 
- define how a [[py object]] reacts when certain functions or operands are applied 

#### [[py callable object]]: 
- how an [[py object]] reacts when `object()` is called is defined in the `__call__` method of the object

#### [[py comparison operations]]: 
- how the [[py object]] reacts when comparision operators are used. E.g.  `object1 >= object2` behavour is impelemented in the `__geq__` [[py magic method]]

#### how the [[py object]] reacts when [[py unary operators]] are used
![[py unary operators]]

#### [[py binary operations]]: how the [[py object]] reacts when binary  operators are used
![[py binary operations]]

#### [[py object creation]]

![[py object creation#object creation]]

#### [[py container objects]]
`__len__` : returns the length of the container 
`__getitem__`  Defines behavior for when an item is accessed, using the notation `self[key]`. 
`__setitem__` Defines behavior for when an item is assigned to, using the notation `self[nkey] = value`. 
`__delitem__` Defines behavior for when an item is deleted (e.g. `del self[key]`). 

#### [[py type conversion]]
![[py type conversion]]

# Anki
START
Basic
[[python]] [[py magic method]] summary
- definition
- object creation (3)
- function call (1)
- comparision (1)
- operators (3 + 3)
- conversion (2)

Back: 
#### defintion
- define how a [[py object]] reacts when certain functions or operands are applied 

#### [[py callable object]]: 
- how an [[py object]] reacts when `object()` is called is defined in the `__call__` method of the object

#### [[py object creation]]

`__new__(cls, [...)`: 
- first method called in [[py object creation]]
- - recives a reference to the [[py class]] (`cls`) plus all the arguments passed during the object creation call
`__init__(self, [...)`: 
- first method that is called after the [[py object]] is instanciated 
- recives a reference to the instance itself (`self`) plus all the arguments passed during the object creation call
`__del__(self)`: destructor that is called when object is deleted 

#### [[py container objects]]
immutuable
`__len__` : returns the length of the container 
`__getitem__`  Defines behavior for when an item is accessed, using the notation `self[key]`. 
mutuable
`__setitem__` Defines behavior for when an item is assigned to, using the notation `self[nkey] = value`. 
`__delitem__` Defines behavior for when an item is deleted (e.g. `del self[key]`). 


####  [[py comparison operations]]: 
- how the [[py object]] reacts when comparision operators are used. E.g.  `object1 >= object2` behavour is impelemented in the `__geq__` [[py magic method]]

#### how the [[py object]] reacts when [[py unary operators]] are used
- `__neg__()`: Implements behavior for negation (e.g. `-some_object`)
- `__abs__()`: Implements behavior for the built in `abs()` function.
- `__invert__()`: Implements behavior for inversion using the `~` operator. 
- `__round__(self, n)`: Implements behavior for the built in `round()` function

#### [[py binary operations]]: how the [[py object]] reacts when binary  operators are used
- `__add__(self, other)`: Implements addition.
- `__sub__(self, other)`: Implements subtraction.
- `__mul__(self, other)`: Implements multiplication
- `__mod__(self, other)`: Implements modulo using the `%` operator.
- `__and__(self, other)`:Implements bitwise and using the `&` operator.
- `__or__(self, other)`: Implements bitwise or using the `|` operator.

#### [[py type conversion]]
`__int__(self)` Implements type conversion to int.
`__long__(self)`:Implements type conversion to long.
`__float__(self)`: Implements type conversion to float.


Tags: code python
<!--ID: 1698602509085-->
END