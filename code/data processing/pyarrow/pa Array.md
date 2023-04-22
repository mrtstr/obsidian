## Concept
- immutable collection of in-memory data of the same [[pa datatype]]
- contains multiple [[pa Buffer]] and imposes some sort of semantics into them (data type)
- Arrays are "contiguous" in the sense that each [[pa Buffer]] is contiguous
- can be sliced without copying (→ creates reference to memory)
- can hold [[pa Scalar]] or [[pa nested structure]]


## factory functions
### from [[pa Array]], [[np array]], [[py interatable]]
```python
pa.array(
	obj, # sequenze/itertbale/array containing the data
	type, # datatype
	size, # max size
	safe, # bool: Check for overflows or other unsafe conversions
	memory_pool, # where to allocate the memory
)
```
#### example
```python
days = pa.array([1, 12, 17, 23, 28], type=pa.int8())
months = pa.array([1, 3, 5, 7, 1], type=pa.int8())
years = pa.array([1990, 2000, 1995, 2000, 1995], type=pa.int16())
```
### from [[pa Buffer]]
```python
pa.array.from_buffers(
	buffers, # list of buffers
	type, # datatype
	length, # lenth of resulting array
)
```
### from [[pd series]]
```python
pa.array.from_pandas(
	_obj_, # pandas series
	type, # datatype
	length, # lenth of resulting array
)
```
## attributes
```python
nbytes # Total number of bytes consumed by the elements of the array.
type   # logical datatype
null_count # number of null values in array
```
## methods
```python
.buffers() # list of Buffer objects pointing to this array’s physical storage
.cast(              # Cast array values to another data type
	  target_type,  # type to last to
	  safe=True,    # check for conversion errors such as overflow
	  options=None. # Additional checks pass by CastOptions
)
.index(value)  # Find the first index of a value.
.dictionary_encode()  # Compute dictionary-encoded (categorical data) representation of array
.length() # return length of array
.diff(). # compare to other array
.filter(mask) # filter array using a mask
.fill_null(fill_value) # fill null values will the fill vaue
.is_null(). # Return BooleanArray indicating the null values.
.is_valid() # Return BooleanArray indicating the non-null values.
.silce(sice) # Compute zero-copy slice of this array.
.sort() # sort this array
.value_counts() # Compute counts of unique elements in array.
.sum()  # calulate a sum over the array
.take(indices)  #  Select values from an array
.to_numpy() #. return a numpy array
.to_pylist()  # return a python list
.to_string() # printable string represtantion
.unique()   # Compute distinct elements in array.
.view()     # Return zero-copy "view" of array as another data type.
.validate() # Perform validation checks.
```

# Anki
START
Basic
[[pa Array]]: how to create it 
- 3 data sources
- arguments (5)
Back: 
## How to create it
### from [[pa Array]], [[np array]], [[py interatable]]
```python
pa.array(
	obj, # sequenze/itertbale/array containing the data
	type, # datatype
	size, # max size
	safe, # bool: Check for overflows or other unsafe conversions
	memory_pool, # where to allocate the memory
)
```
#### example
```python
days = pa.array([1, 12, 17, 23, 28], type=pa.int8())
months = pa.array([1, 3, 5, 7, 1], type=pa.int8())
years = pa.array([1990, 2000, 1995, 2000, 1995], type=pa.int16())
```
### from [[pa Buffer]]
```python
pa.array.from_buffers(
	buffers, # list of buffers
	type, # datatype
	length, # lenth of resulting array
)
```
### from [[pd series]]
```python
pa.array.from_pandas(
	obj, # pandas series
	type, # datatype
	length, # lenth of resulting array
)
```

Tags: code pyarrow
<!--ID: 1681744599046-->
END


START
Basic
[[pa Array]]: methods
- pointer to phzsical memory (1)
- convert to other data type (2)
- change encoding (1)
- conversions (3)
- length of array (1)
- select data (2)
- sort sum count (3)
- create mask and use mask (3)
- compare arrays (1)
- fill null
- get unique elements
Back: 
```python
.buffers() # list of Buffer objects pointing to this array’s physical storage
## data conversion
.cast(              # Cast array values to another data type
	  target_type,  # type to last to
	  safe=True,    # check for conversion errors such as overflow
	  options=None. # Additional checks pass by CastOptions
)
.view()     # Return zero-copy "view" of array as another data type.

## conversion of object itself
.to_numpy() #. return a numpy array
.to_pylist()  # return a python list
.to_string() # printable string represtantion

.unique()   # Compute distinct elements in array.

.take(indices)  #  Select values from an array
.silce(sice) # Compute zero-copy slice of this array.

.index(value)  # Find the first index of a value.
.dictionary_encode(). # Compute dictionary-encoded (categorical data) representation of array

.length() # return length of array
.diff() # compare to other array
.filter(mask) # filter array using a mask
.fill_null(fill_value) # fill null values will the fill vaue

.is_null(). # Return BooleanArray indicating the null values.
.is_valid() # Return BooleanArray indicating the non-null values.

.sort() # sort this array
.value_counts() # Compute counts of unique elements in array.
.sum()  # calulate a sum over the array

.validate() # Perform validation checks.
```
Tags: code pyarrow
<!--ID: 1681744599049-->
END

START
Basic
[[pa Array]]
- concept and properties (2)
- memory organisation
- attributes (3)

Back: 
## concept
- immutable collection of in-memory data of the same [[pa datatype]]
- contains multiple [[pa Buffer]] and imposes some sort of semantics into them (data type)
- Arrays are "contiguous" in the sense that each [[pa Buffer]] is contiguous
- can be sliced without copying (→ creates reference to memory)
- can hold values or [[pa nested structure]]
## attributes
```python
nbytes # Total number of bytes consumed by the elements of the array.
type   # logical datatype
null_count # number of null values in array
```
Tags: code pyarrow
<!--ID: 1681037725711-->
END