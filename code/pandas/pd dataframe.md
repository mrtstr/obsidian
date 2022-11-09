- two dimensional labeled data structure [[pd index]] on axis 0 and [[pd column]] on axis 1
- [[pd index]] and [[pd column]] are stored as wrapped [[np ndarray]]
- columns can have different [[pd dtype|dtypes]] but need to have the same [[pd index]]
- is like a [[py dict|dict]] of [[pd series|series]]
```python
pd_df["colname"]["indexname"]
```
- the underlaying data structure of the [[pd dataframe]] is the [[np ndarray]] and can be accessed and manipulated using [[pd dataframe|dataframe]].values

```python
display(pd_df1)
#  col1 col2 col3
# a   1   5   9
# b   2   6   10
# c   3   7   11
# d   4   8   12
pd_df1.values[1,1] = 99
display(pd_df1)
#  col1 col2 col3
# a   1   5   9
# b   2   99   10
# c   3   7   11
# d   4   8   12
```

## example df
```python
pd_df1 = pd.DataFrame({
	"col1": {"a": 1, "b":2, "c":3, "d":4},
	"col2": {"a": 5, "b":6, "c":7, "d":8},
	"col3": {"a": 9, "b":10, "c":11, "d":12},
})
  
#  col1 col2 col3
# a   1   5   9
# b   2   6   10
# c   3   7   11
# d   4   8   12
```



# anki

START
Basic
pandas dataframe:
- concept 
- labeled axis
- underlaying data manipulation (example)
Back: 
- two dimensional labeled data structure [[pd index]] on axis 0 and [[pd column]] on axis 1
- [[pd index]] and [[pd column]] are stored as wrapped [[np ndarray]]
- columns can have different [[pd dtype|dtypes]] but need to have the same [[pd index]]
- is like a [[py dict|dict]] of [[pd series|series]]
```python
pd_df["colname"]["indexname"]
```
- the underlaying data structure of the [[pd dataframe]] is the [[np ndarray]] and can be accessed and manipulated using [[pd dataframe|dataframe]].values
```python
display(pd_df1)
#  col1 col2 col3
# a   1   5   9
# b   2   6   10
# c   3   7   11
# d   4   8   12
pd_df1.values[1,1] = 99
display(pd_df1)
#  col1 col2 col3
# a   1   5   9
# b   2   99   10
# c   3   7   11
# d   4   8   12
```
Tags: code, pandas
<!--ID: 1668010184541-->
END