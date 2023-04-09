## concept
- [[pyarrow]] [[array]] are one dimensional collections of data of the same [[pa datatype]]
- the data in a [[pa Array]] is immutable
- Each in-memory array has a known length
- can be sliced without copying

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
## methods

## example

### [[pa Array]] containing [[pa Struct]] (and infer its schema)

```python
struct_array = pa.array([{'x': 1, 'y': True}, {'z': 3.4, 'x': 4}])
# -- child 0 type: int64
#  [    1,    4  ]
# -- child 1 type: bool
#  [    true,    null  ]
# -- child 2 type: double
#  [    null,    3.4  ]
```
### [[pa Array]] containing [[pa List]]
```python
list_array = pa.array([[1,2,3], [4,5,6], None])
list_array.type
# ListType(list<item: int64>)
```

START
Basic
[[pa Array]]
- conect
- how to manupulate
- example:
	- create [[pa Array]]
	- sum up [[pa Array]]
Back: 
- [[pyarrow]] [[array]] are one dimensional collections of data of the same [[pa datatype]]
- can be manupulated with functions from [[pa compute]]

### example arrays: creating a [[pa Array]] from a [[py list]]
```python
days = pa.array([1, 12, 17, 23, 28], type=pa.int8())
months = pa.array([1, 3, 5, 7, 1], type=pa.int8())
years = pa.array([1990, 2000, 1995, 2000, 1995], type=pa.int16())
```
### example sum up [[pa Array]]
```python
import pyarrow.compute as pc
pc.sum(days)
```
Tags: code pyarrow
<!--ID: 1681037725711-->
END