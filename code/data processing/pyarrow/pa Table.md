## Table
- same properties as a [[pa RecordBatch]] but can contrain one or multiple [[pa RecordBatch|pa RecordBatchs]] of the same [[pa Schema]] that are logicly treated as one
- tool for wrangling multiple [[pa RecordBatch|pa RecordBatchs]] and [[pa Array]] pieces as a single logical dataset
- can contrain one or multiple [[pa RecordBatch|pa RecordBatchs]] 
	→ in case of multiple [[pa RecordBatch|pa RecordBatchs]] the data is saved in [[pa ChunkedArray|pa ChunkedArrays]]

![[pa RecordBatch#RecordBatch]]


## example
- creating a [[pa Table]] from duplicated [[pa RecordBatch|pa RecordBatchs]]
- the data ist stored in [[pa ChunkedArray]]
```python
table = pa.Table.from_batches([batch]*3)
table.column("col1")
# <pyarrow.lib.ChunkedArray object at 0x7f4364d0bb50> 
# [ [ 1, 2, 3, 4 ], [ 1, 2, 3, 4 ], [ 1, 2, 3, 4 ] ]
```

| col1 | col2 | col3 | 
|-------:|:-------|:-------| 
| 1 | foo | True | 
| 2 | bar | | 
| 3 | baz | False | 
| 4 | | True | 
| 1 | foo | True | 
| 2 | bar | | 
| 3 | baz | False | 
| 4 | | True | 
| 1 | foo | True | 
| 2 | bar | | 
| 3 | baz | False | 
| 4 | | True |


# anki

START
Basic
[[pa Table]]
- concept
- attributes (5)
- relationship to [[pa RecordBatch]]
- example: create [[pa Table]] from multiple [[pa RecordBatch|pa RecordBatchs]]
	- how is the data saved?
Back: 

## concept
- same properties as a [[pa RecordBatch]] but can contrain one or multiple [[pa RecordBatch|pa RecordBatchs]] of the same [[pa Schema]] that are logicly treated as one
- tool for wrangling multiple [[pa RecordBatch|pa RecordBatchs]] and [[pa Array]] pieces as a single logical dataset
- can contrain one or multiple [[pa RecordBatch|pa RecordBatchs]] 
	→ in case of multiple [[pa RecordBatch|pa RecordBatchs]] the data is saved in [[pa ChunkedArray|pa ChunkedArrays]]

## RecordBatch
- A [[pa RecordBatch]] is a collection of equal-length [[pa Array]] instances
- has a [[pa Schema]] contraining additional information for each [[pa Array]]
- column based data organisizion makes operations more efficient
- can be loaded from either the disk (memory mapped) or in memory
### Attributes
```python
columns # List of all columns in numerical order.
num_columns # Number of columns in this table.
num_rows # Number of rows in this table.
schema # Schema of the table and its columns (names and data types).
nbytes # Total number of bytes consumed by the elements of the table.
```

### examples

```python
data = [
	pa.array([1, 2, 3, 4]),
	pa.array(['foo', 'bar', 'baz', None]),
	pa.array([True, None, False, True])
]

batch = pa.RecordBatch.from_arrays(
	arrays = data,
	names = ['col1', 'col2', 'col3']
)
```

| col1 | col2 | col3 | 
|-------:|:-------|:-------| 
| 1 | foo | True | 
| 2 | bar | null | 
| 3 | baz | False | 
| 4 | null | True |


## example
- creating a [[pa Table]] from duplicated [[pa RecordBatch|pa RecordBatchs]]
- the data ist stored in [[pa ChunkedArray]]
```python
table = pa.Table.from_batches([batch]*3)
table.column("col1")
# <pyarrow.lib.ChunkedArray object at 0x7f4364d0bb50> 
# [ [ 1, 2, 3, 4 ], [ 1, 2, 3, 4 ], [ 1, 2, 3, 4 ] ]
```

| col1 | col2 | col3 | 
|-------:|:-------|:-------| 
| 1 | foo | True | 
| 2 | bar | | 
| 3 | baz | False | 
| 4 | | True | 
| 1 | foo | True | 
| 2 | bar | | 
| 3 | baz | False | 
| 4 | | True | 
| 1 | foo | True | 
| 2 | bar | | 
| 3 | baz | False | 
| 4 | | True |


Tags: code pyarrow
<!--ID: 1681037725703-->
END