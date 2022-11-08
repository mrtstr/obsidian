- two dimensional labeled data structure 
- columns can have different [[pd dtype|dtypes]]
- is like a [[py dict|dict]] of [[pd series|series]] 

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
