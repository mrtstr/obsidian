[[py function]] are [[py callable object|callable]] [[py object]] from the class `function`

![[py callable object#py callable object]]

### [[py dunder valiables]] [[py function]]
- `__name__`: stores the name of the [[py function]]
-   `__module__`: stores the name of the module they were defined in within
-   `__defaults__` and `__kwdefaults__`: store their default argument values

![[py object#py dunder valiables py object]]


# anki

START
Basic
[[py function]]
- definition
- [[py dunder valiables]] (6)
Back: 
[[py function]] are [[py callable object|callable]] [[py object]] from the class `function`

#### [[py callable object]]
[[python]] [[py object]] that has the [[py dunder method]] `_call__(self, [args...])` implemented

```python
class CallableObject(object):
	def __init__(self, value=0.0):
		self.value = value
	
	def __call__(self, add_val):
		return self.value + add_val

myfunction = CallableObject(2)

myfunction(1) # reaturn 3
```


### [[py dunder valiables]] [[py function]]
- `__name__`: stores the name of the [[py function]]
-   `__module__`: stores the name of the module they were defined in within
-   `__defaults__` and `__kwdefaults__`: store their default argument values

#### [[py dunder valiables]] [[py object]]
-   `__class__`: stores the [[py class]] of the [[py object]] 
-   `__dict__`: stores the attributes of the [[py object]]

Tags: code python
<!--ID: 1698748522698-->
END