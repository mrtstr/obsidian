## Concept
- [[pyarrow]] [[dataframe]] is a collection of named [[pa array|pa arrays]] of the same length

## example: creating a [[pa table]] from [[pa array|pa arrays]]
![[pa array#example arrays]]

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
[[pa table]]
- [[pyarrow]] [[dataframe]] is a collection of named [[pa array|pa arrays]] of the same length
- example: create a [[pa table]]
Back: 
- [[pyarrow]] [[dataframe]] is a collection of named [[pa array|pa arrays]] of the same length
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