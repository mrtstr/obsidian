## RecordBatch
- collection of [[pa Array]] of the same length with a [[pa Schema]] (contraining additional information for each [[pa Array]])
- continous memory representation -> cannot be concated [[zero copy]]

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
- conecept + memory organisation
- relationship to [[pa Schema]]
- attributes (5)

Back: 

- collection of [[pa Array]] of the same length with a [[pa Schema]] (contraining additional information for each [[pa Array]])
- continous memory representation → cannot be concated [[zero copy]]


## Attributes
```python
columns # List of all columns in numerical order.
num_columns # Number of columns in this table.
num_rows # Number of rows in this table.
schema # Schema of the table and its columns (names and data types).
nbytes # Total number of bytes consumed by the elements of the table.
```

Tags: code pyarrow
<!--ID: 1681116775356-->
END