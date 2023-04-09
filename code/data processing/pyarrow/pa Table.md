## Concept
- [[pyarrow]] [[dataframe]] is a collection of named [[pa Array|pa arrays]] of the same length
- each column has a [[pa Array]] containing the data and a [[pa Field]] containing additional information like column name
- column based data organisizion makes operations more efficient
- can be loaded from either the disk (memory mapped) or in memory
## Attributes
```python
column_names # Names of the table's columns.
columns # List of all columns in numerical order.
num_columns # Number of columns in this table.
num_rows # Number of rows in this table.
shape # Dimensions of the table: (#rows, #columns).
schema # Schema of the table and its columns (names and data types).
nbytes # Total number of bytes consumed by the elements of the table.
type   # logical datatype
```

## example: creating a [[pa Table]] from [[pa Array|pa arrays]]
![[pa Array#example]]

```python
df = pa.table(
  [days, months, years], 
  names = ["days", "months", "years"]
)
```

| days | months | years | 
|-------:|---------:|--------:| 
| 1 | 1 | 1990 | 
| 12 | 3 | 2000 | 
| 17 | 5 | 1995 | 
| 23 | 7 | 2000 | 
| 28 | 1 | 1995 |


# anki

START
Basic
[[pa Table]]
- [[pyarrow]] [[dataframe]] is a collection of named [[pa Array|pa arrays]] of the same length
- example: create a [[pa Table]]
Back: 
- [[pyarrow]] [[dataframe]] is a collection of named [[pa Array|pa arrays]] of the same length
- [[pyarrow]] [[array]] are one dimensional collections of data of the same [[pa datatype]]
```python
days = pa.array([1, 12, 17, 23, 28], type=pa.int8())
months = pa.array([1, 3, 5, 7, 1], type=pa.int8())
years = pa.array([1990, 2000, 1995, 2000, 1995], type=pa.int16())

df = pa.table(
  [days, months, years], 
  names = ["days", "months", "years"]
)
```

| days | months | years | 
|-------:|---------:|--------:| 
| 1 | 1 | 1990 | 
| 12 | 3 | 2000 | 
| 17 | 5 | 1995 | 
| 23 | 7 | 2000 | 
| 28 | 1 | 1995 |

Tags: code pyarrow
<!--ID: 1681037725703-->
END