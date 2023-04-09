- Batch of rows of columns of equal length
- [[pa Table]] like structure
- semantically a sequence of [[pa Field]], each a contiguous Arrow array
## Attributes
```python
columns # List of all columns in numerical order.
num_columns # Number of columns in this table.
num_rows # Number of rows in this table.
schema # Schema of the table and its columns (names and data types).
nbytes # Total number of bytes consumed by the elements of the table.

```