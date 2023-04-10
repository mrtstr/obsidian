## concept
- [[pyarrow]] [[array]] are one dimensional collections of data of the same [[pa datatype]]
- the data in a [[pa Array]] is in-memory and immutable
- can be sliced without copying (→ creates reference to memory)
- can hold values or nested structures 
	-  [[pa Scalar]] values
	- [[pa ListArray]] holding [[pa ListType]] elements
	- [[pa MapArray]] holding [[pa MapType]] elements
	- [[pa StructArray]] holding [[pa StructType]] elements
	- [[pa DictionaryArray]] holding [[pa DictionaryType]] elements ([[categorical data]])

## example
```python
days = pa.array([1, 12, 17, 23, 28], type=pa.int8())
months = pa.array([1, 3, 5, 7, 1], type=pa.int8())
years = pa.array([1990, 2000, 1995, 2000, 1995], type=pa.int16())
```

## attributes
```python
nbytes # Total number of bytes consumed by the elements of the array.
type   # logical datatype
null_count # number of null values in array
```



# Anki

START
Basic
[[pa Array]]
- concept and properties (1 + 3)
- what data structures it can hold (5)
- attributes (3)
- example: create [[pa Array]]
]
Back: 
## concept
- [[pyarrow]] [[array]] are one dimensional collections of data of the same [[pa datatype]]
- the data in a [[pa Array]] is in-memory and immutable
- can be sliced without copying (→ creates reference to memory)
- can hold values or nested structures 
	-  [[pa Scalar]] values
	- [[pa ListArray]] holding [[pa ListType]] elements
	- [[pa MapArray]] holding [[pa MapType]] elements
	- [[pa StructArray]] holding [[pa StructType]] elements
	- [[pa DictionaryArray]] holding [[pa DictionaryType]] elements ([[categorical data]])

## example
```python
days = pa.array([1, 12, 17, 23, 28], type=pa.int8())
months = pa.array([1, 3, 5, 7, 1], type=pa.int8())
years = pa.array([1990, 2000, 1995, 2000, 1995], type=pa.int16())
```

## attributes
```python
nbytes # Total number of bytes consumed by the elements of the array.
type   # logical datatype
null_count # number of null values in array
```
Tags: code pyarrow
<!--ID: 1681037725711-->
END