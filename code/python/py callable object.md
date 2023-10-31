### [[py callable object]]
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

# Anki
START
Basic
[[py callable object]]
- definition
- how to make an object callable
Back: 
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
Tags: code python
<!--ID: 1698602509063-->
END