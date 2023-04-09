[[pyarrow]] [[array]] are collections of data of the same [[pa datatype]]

creating a [[pa array]] from a [[py list]]
```python
days = pa.array([1, 12, 17, 23, 28], type=pa.int8())
```