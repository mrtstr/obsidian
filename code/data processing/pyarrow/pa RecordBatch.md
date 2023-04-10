## RecordBatch
- A [[pa RecordBatch]] is a collection of equal-length [[pa Array]] instances
- has a [[pa Schema]] contraining additional information for each [[pa Array]]
- column based data organisizion makes operations more efficient
- can be loaded from either the disk (memory mapped) or in memory
![[pa Schema#Schema]]

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


# anki

START
Basic
[[pa RecordBatch]]
- conecept
- relationship to [[pa Schema]]
- memory organisation
- two ways how to load it
- attributes (5)
- example: create a [[pa RecordBatch]] from [[pa Array|pa Arrays]]
Back: 
# RecordBatch
- A [[pa RecordBatch]] is a collection of equal-length [[pa Array]] instances
- has a [[pa Schema]] contraining additional information for each [[pa Array]]
- column based data organisizion makes operations more efficient
- can be loaded from either the disk (memory mapped) or in memory

### Schema
- A [[pa Schema]] is a collection of named [[pa Field|pa Fields]]

### Field
- defines a placeholder for data
- [[pa Field]] holds [[pa datatype]] and additional properties of values
- in addtion to a [[pa datatype]]
```python
name      # name of column
nullable  # nullable or not
type      # datatype
```
- each [[pa Field]] holding additional information of a [[pa Array]] and both togather are a column
- similar to a [[pa StructType]]

#### example
```python
fields = [
	pa.field('id', pa.int32()),
	pa.field('first_name', pa.string()),
	pa.field('last_name', pa.string()),
]
schema1 = pa.schema(fields)
schema1 = pa.schema(    # shorter
   [
	   ('id', pa.int32()), 
	   ('first_name', pa.string()), 
	   ('last_name', pa.string()), ('s3', pa.string())
   ]
)
```

## Attributes
```python
columns # List of all columns in numerical order.
num_columns # Number of columns in this table.
num_rows # Number of rows in this table.
schema # Schema of the table and its columns (names and data types).
nbytes # Total number of bytes consumed by the elements of the table.
```

## examples

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



Tags: code pyarrow
<!--ID: 1681116775356-->
END