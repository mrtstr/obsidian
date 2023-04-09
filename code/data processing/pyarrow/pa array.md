- [[pyarrow]] [[array]] are one dimensional collections of data of the same [[pa datatype]]
- can be manupulated with functions from [[pa compute]]

### example arrays: creating a [[pa array]] from a [[py list]]
```python
days = pa.array([1, 12, 17, 23, 28], type=pa.int8())
months = pa.array([1, 3, 5, 7, 1], type=pa.int8())
years = pa.array([1990, 2000, 1995, 2000, 1995], type=pa.int16())
```

START
Basic
[[pa array]]
- conect
- how to manupulate
- example:
	- create [[pa array]]
	- sum up [[pa array]]
Back: 
- [[pyarrow]] [[array]] are one dimensional collections of data of the same [[pa datatype]]
- can be manupulated with functions from [[pa compute]]

### example arrays: creating a [[pa array]] from a [[py list]]
```python
days = pa.array([1, 12, 17, 23, 28], type=pa.int8())
months = pa.array([1, 3, 5, 7, 1], type=pa.int8())
years = pa.array([1990, 2000, 1995, 2000, 1995], type=pa.int16())
```
### example sum up [[pa array]]
```python
import pyarrow.compute as pc
pc.sum(days)
```
Tags: code pyarrow
<!--ID: 1681037725711-->
END