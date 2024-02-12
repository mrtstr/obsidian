
# [[py container objects]]

Making [[py class]] to act like built in sequences like
- [[py list]]
- [[py set]]
- [[py tuple]]
- ...

## base (immutable) containers
### protocol for base (immutable) containers
#### `__len__` 
- returns the length of the container 
 
#### `__getitem__`  
Defines behavior for when an item is accessed, using the notation `self[key]`. It should also raise appropriate exceptions: `TypeError` if the type of the key is wrong and `KeyError` if there is no corresponding value for the key.

### example base (immutable) [[py container objects]]
```python
class BaseContainer():
	def __init__(self, *args):
		self.values = args
	
	def __len__(self):
		print(f"The __len__ method was called")
		return len(self.values)
	
	def __getitem__(self, index):
		print(f"The __getitem_ method was called")
		index = int(index)
		if index < len(self) and index >= 0:
			print(f"returning element with index {index}")
			return self.values[index]
		raise KeyError(f"index {index} out of bound")

my_base_container = BaseContainer(11,22,33)

len(my_base_container)
# The __len__ method was called 
# 3
my_base_container[1]
# The __getitem_ method was called 
# The __len__ method was called returning element with index 1 
# 22
my_base_container[7]
# The __getitem_ method was called 
# The __len__ method was called
# KeyError: index 7 out of bound
```

## mutable containers
- implement the container protocol plus the  protocol for mutable containers
### protocol for mutable containers

#### `__setitem__` 
Defines behavior for when an item is assigned to, using the notation `self[nkey] = value`. This is part of the mutable container protocol. Again, you should raise `KeyError` and `TypeError` where appropriate.
#### `__delitem__`. 
Defines behavior for when an item is deleted (e.g. `del self[key]`). This is only part of the mutable container protocol. You must raise the appropriate exceptions when an invalid key is used.

### example mutable [[py container objects]]
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

my_mutable_container[1] = 99
# The __setitem__ method was called 
# The __len__ method was called setting 99 to nkey 1 
# [11, 99, 33]
del my_mutable_container[0]
# The __delitem__ method was called 
# The __len__ method was called 
# removing 11 
# [99, 33]
```


## [[py interatable]] containers
- implement the container plus the [[py interatable]] protocol

![[py interatable#py interatable protocol]]

### example
```python
class IterableContainer(BaseContainer):
	def __iter__(self):
		print("__iter__ method was called")
		for i in range(len(self)):
			yield self.values[i]

my_iterable_container = IterableContainer(11,22,33)

for i in my_iterable_container:
	print(i)

# __iter__ method was called 
# The __len__ method was called 
# 11 
# 22 
# 33
```

## additional [[py dunder method]]
#### `__reversed__(self)`
Called to implement behavior for the `reversed()` built in function. Should return a reversed version of the sequence. 

#### `__contains__(self, item)`
Defines behavior for membership tests using `in` and `not in`. 

# Anki
START
Basic
[[py container objects]]
- types with protocols (3)
- additional functions (2)
Back: 
Making [[py class]] to act like built in sequences like
- [[py list]]
- [[py set]]
- [[py tuple]]
- ...

## base (immutable) containers
### protocol for base (immutable) containers
#### `__len__` 
- returns the length of the container 
 
#### `__getitem__`  
Defines behavior for when an item is accessed, using the notation `self[key]`. It should also raise appropriate exceptions: `TypeError` if the type of the key is wrong and `KeyError` if there is no corresponding value for the key.

## mutable containers
- implement the container protocol plus the  protocol for mutable containers

### protocol for mutable containers

#### `__setitem__` 
Defines behavior for when an item is assigned to, using the notation `self[nkey] = value`. This is part of the mutable container protocol. Again, you should raise `KeyError` and `TypeError` where appropriate.
#### `__delitem__`. 
Defines behavior for when an item is deleted (e.g. `del self[key]`). This is only part of the mutable container protocol. You must raise the appropriate exceptions when an invalid key is used.


## [[py interatable]] containers

#### [[py interatable]] protocol
#### `__iter__()`
- usually called by the [[py buidin functions|buidin function inter()]] to convert a [[py interatable]] into an [[py iterator]]. 


## additional [[py dunder method]]
#### `__reversed__(self)`
Called to implement behavior for the `reversed()` built in function. Should return a reversed version of the sequence. 

#### `__contains__(self, item)`
Defines behavior for membership tests using `in` and `not in`. 

```python
class BaseContainer():
	def __init__(self, *args):
		self.values = args
	
	def __len__(self):
		print(f"The __len__ method was called")
		return len(self.values)
	
	def __getitem__(self, index):
		print(f"The __getitem_ method was called")
		index = int(index)
		if index < len(self) and index >= 0:
			print(f"returning element with index {index}")
			return self.values[index]
		raise KeyError(f"index {index} out of bound")

my_base_container = BaseContainer(11,22,33)

len(my_base_container)
# The __len__ method was called 
# 3
my_base_container[1]
# The __getitem_ method was called 
# The __len__ method was called returning element with index 1 
# 22
my_base_container[7]
# The __getitem_ method was called 
# The __len__ method was called
# KeyError: index 7 out of bound
```

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

my_mutable_container[1] = 99
# The __setitem__ method was called 
# The __len__ method was called setting 99 to nkey 1 
# [11, 99, 33]
del my_mutable_container[0]
# The __delitem__ method was called 
# The __len__ method was called 
# removing 11 
# [99, 33]
```


```python
class IterableContainer(BaseContainer):
	def __iter__(self):
		print("__iter__ method was called")
		for i in range(len(self)):
			yield self.values[i]

my_iterable_container = IterableContainer(11,22,33)

for i in my_iterable_container:
	print(i)

# __iter__ method was called 
# The __len__ method was called 
# 11 
# 22 
# 33
```

Tags: code python
<!--ID: 1698602509069-->
END


START
Basic
[[py container objects]] immutable (base container)
- protocol
- example
Back: 

## base (immutable) containers
### protocol for base (immutable) containers
#### `__len__` 
- returns the length of the container 
 
#### `__getitem__`  
Defines behavior for when an item is accessed, using the notation `self[key]`. It should also raise appropriate exceptions: `TypeError` if the type of the key is wrong and `KeyError` if there is no corresponding value for the key.

```python
class BaseContainer():
	def __init__(self, *args):
		self.values = args
	
	def __len__(self):
		print(f"The __len__ method was called")
		return len(self.values)
	
	def __getitem__(self, index):
		print(f"The __getitem_ method was called")
		index = int(index)
		if index < len(self) and index >= 0:
			print(f"returning element with index {index}")
			return self.values[index]
		raise KeyError(f"index {index} out of bound")

my_base_container = BaseContainer(11,22,33)

len(my_base_container)
# The __len__ method was called 
# 3
my_base_container[1]
# The __getitem_ method was called 
# The __len__ method was called returning element with index 1 
# 22
my_base_container[7]
# The __getitem_ method was called 
# The __len__ method was called
# KeyError: index 7 out of bound
```


Tags: code python
<!--ID: 1698602509072-->
END



START
Basic
[[py container objects]] mutable container
- protocol
- example
Back: 

## mutable containers
- implement the container protocol plus the  protocol for mutable containers
### protocol for mutable containers

#### `__setitem__` 
Defines behavior for when an item is assigned to, using the notation `self[nkey] = value`. This is part of the mutable container protocol. Again, you should raise `KeyError` and `TypeError` where appropriate.
#### `__delitem__`. 
Defines behavior for when an item is deleted (e.g. `del self[key]`). This is only part of the mutable container protocol. You must raise the appropriate exceptions when an invalid key is used.

### example for mutable containers
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

my_mutable_container[1] = 99
# The __setitem__ method was called 
# The __len__ method was called setting 99 to nkey 1 
# [11, 99, 33]
del my_mutable_container[0]
# The __delitem__ method was called 
# The __len__ method was called 
# removing 11 
# [99, 33]
```


## base (immutable) containers
### protocol for base (immutable) containers
#### `__len__` 
- returns the length of the container 
 
#### `__getitem__`  
Defines behavior for when an item is accessed, using the notation `self[key]`. It should also raise appropriate exceptions: `TypeError` if the type of the key is wrong and `KeyError` if there is no corresponding value for the key.

```python
class BaseContainer():
	def __init__(self, *args):
		self.values = args
	
	def __len__(self):
		print(f"The __len__ method was called")
		return len(self.values)
	
	def __getitem__(self, index):
		print(f"The __getitem_ method was called")
		index = int(index)
		if index < len(self) and index >= 0:
			print(f"returning element with index {index}")
			return self.values[index]
		raise KeyError(f"index {index} out of bound")

my_base_container = BaseContainer(11,22,33)

len(my_base_container)
# The __len__ method was called 
# 3
my_base_container[1]
# The __getitem_ method was called 
# The __len__ method was called returning element with index 1 
# 22
my_base_container[7]
# The __getitem_ method was called 
# The __len__ method was called
# KeyError: index 7 out of bound
```


Tags: code python
<!--ID: 1698602509076-->
END


START
Basic
[[py interatable]] [[py container objects]] 
- protocol
- example
Back: 
#### [[py interatable]] containers
- implement the container plus the [[py interatable]] protocol

#### [[py interatable]] protocol
#### `__iter__()`
- usually called by the [[py buidin functions|buidin function inter()]] to convert a [[py interatable]] into an [[py iterator]]. 

### example
```python
class IterableContainer(BaseContainer):
	def __iter__(self):
		print("__iter__ method was called")
		for i in range(len(self)):
			yield self.values[i]

my_iterable_container = IterableContainer(11,22,33)

for i in my_iterable_container:
	print(i)

# __iter__ method was called 
# The __len__ method was called 
# 11 
# 22 
# 33
```


## base (immutable) containers
### protocol for base (immutable) containers
#### `__len__` 
- returns the length of the container 
 
#### `__getitem__`  
Defines behavior for when an item is accessed, using the notation `self[key]`. It should also raise appropriate exceptions: `TypeError` if the type of the key is wrong and `KeyError` if there is no corresponding value for the key.

```python
class BaseContainer():
	def __init__(self, *args):
		self.values = args
	
	def __len__(self):
		print(f"The __len__ method was called")
		return len(self.values)
	
	def __getitem__(self, index):
		print(f"The __getitem_ method was called")
		index = int(index)
		if index < len(self) and index >= 0:
			print(f"returning element with index {index}")
			return self.values[index]
		raise KeyError(f"index {index} out of bound")

my_base_container = BaseContainer(11,22,33)

len(my_base_container)
# The __len__ method was called 
# 3
my_base_container[1]
# The __getitem_ method was called 
# The __len__ method was called returning element with index 1 
# 22
my_base_container[7]
# The __getitem_ method was called 
# The __len__ method was called
# KeyError: index 7 out of bound
```

Tags: code python
<!--ID: 1698602509080-->
END