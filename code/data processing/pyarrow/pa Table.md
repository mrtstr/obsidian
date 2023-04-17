## Table
- same properties as a [[pa RecordBatch]] but can contrain one or multiple [[pa RecordBatch|pa RecordBatchs]] of the same [[pa Schema]] that are logicly treated as one
- tool for wrangling multiple [[pa RecordBatch|pa RecordBatchs]] and [[pa Array]] pieces as a single logical dataset
- can contrain one or multiple [[pa RecordBatch|pa RecordBatchs]] 
	→ in case of multiple [[pa RecordBatch|pa RecordBatchs]] the data is saved in [[pa ChunkedArray|pa ChunkedArrays]]

![[pa RecordBatch#RecordBatch]]

## how to create a [[pa Table]]
- `pa.array.from_arrays()`
- `pa.array.from_batches()`
- `pa.array.from_pandas()`
- `pa.array.from_pydict()`
- `pa.array.from_pylist()`

## convert to other data types
- `.to_batchen()`: convert to [[py list]] of [[pa RecordBatch]]
- `.to_pandas()` convert to [[pd dataframe]]
- `.to_pydict()`: convert to nested [[py dict]]
- `.to_pylist()`: convert to nested [[py list]]
- `.to_string()`: printable string representation

## Methods
### change table
```python
.add_column(loc, field, column) # isert column at position i
.append_column(field, column). # isert column at position last position
.remove_column(i) # create a new table with column in removed
.rename_columns(names) # replace column names with given list of column names
.set_column(i, column) # replace the column i with the given column
.sort_by(columns) # sort by one of multiple columns
.cast(              # Cast array values to another data type
	  target_schema,  # the schema to cast it
	  safe=True,      # check for conversion errors such as overflow
)
.flatten(memory_pool) # Each column with a struct type is flattened into one column per struct field.
.drop(columns) # drop one or more columns
```
### select data
```python
.column(i) # select array of ith column
.itercolumns() # return iterator over columns
.select(columns) # select the culumns given in this list
.take(indices) # select rows with the given indices
.filter(mask) # filter dataframe rows using a mask
```
### chunk ([[pa RecordBatch]] management)
```python
.combine_chunks(memory_pool) # Make a new table by combining the chunks (RecordBatches) this table has.
.unify_dictionaries() # Unify dictionaries across all chunks.
```
### null management
```python
.drop_null() # remove all rows containing nulls
.fill_null(fill_value) # fill null values will the fill vaue
```
### rest
```python
.field(i) # select field of the index i from schema
.equals(other_df) # check of content of two dfs is equal
.validate() # Perform validation checks.
.groupby()
```
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
[[pa Table]]: how to convert it to other data structures (5)
Back: 
- `.to_batchen()`: convert to [[py list]] of [[pa RecordBatch]]
- `.to_pandas()` convert to [[pd dataframe]]
- `.to_pydict()`: convert to nested [[py dict]]
- `.to_pylist()`: convert to nested [[py list]]
- `.to_string()`: printable string representation
Tags: code pyarrow
END


START
Basic
[[pa Table]]: methods for changing it (9)
Back: 
### change table
```python
.add_column(loc, field, column) # isert column at position i
.append_column(field, column). # isert column at position last position
.remove_column(i) # create a new table with column in removed
.rename_columns(names) # replace column names with given list of column names
.set_column(i, column) # replace the column i with the given column
.sort_by(columns) # sort by one of multiple columns
.cast(              # Cast array values to another data type
	  target_schema,  # the schema to cast it
	  safe=True,      # check for conversion errors such as overflow
)
.flatten(memory_pool) # Each column with a struct type is flattened into one column per struct field.
.drop(columns) # drop one or more columns
```

Tags: code pyarrow
END


START
Basic
[[pa Table]]: how to select data
Back: 
### select data
```python
.column(i) # select array of ith column
.itercolumns() # return iterator over columns
.select(columns) # select the culumns given in this list
.take(indices) # select rows with the given indices
.filter(mask) # filter dataframe rows using a mask
```
Tags: code pyarrow
END


START
Basic
[[pa Table]] methods for
- chunk management (2)
- null management (2)
- select properties of row (1)
- compate tables (1)
- check data validity (1)
Back: 
### chunk ([[pa RecordBatch]] management)
```python
.combine_chunks(memory_pool) # Make a new table by combining the chunks (RecordBatches) this table has.
.unify_dictionaries() # Unify dictionaries across all chunks.
```
### null management
```python
.drop_null() # remove all rows containing nulls
.fill_null(fill_value) # fill null values will the fill vaue
```
### rest
```python
.field(i) # select field of the index i from schema
.equals(other_df) # check of content of two dfs is equal
.validate() # Perform validation checks.
.groupby()
```
Tags: code pyarrow
END

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