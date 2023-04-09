Performs a [[transpose]] operation on a [[pd dataframe]]
The [[pd column]] become [[pd index]] and [[pd index]] becomes [[pd column]]
![[pd dataframe#example df]]
```python
pd_df1.T
#      a b c d 
# col1 1 2 3 4 
# col2 5 6 7 8 
# col3 9 10 11 12
```


START
Basic
pandas transpose 
- example
- explaination
Back: 
Performs a [[transpose]] operation on a [[pd dataframe]]
The [[pd column]] become [[pd index]] and [[pd index]] becomes [[pd column]]
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

```python
pd_df1.T
#      a b c d 
# col1 1 2 3 4 
# col2 5 6 7 8 
# col3 9 10 11 12
```
Tags: code pandas
<!--ID: 1667921722432-->
END