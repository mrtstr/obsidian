![[pd dataframe#example df]]
![[pd series#example series]]
## creating a boolean mask 
### using a [[pd series]]
1) a boolean mask on the [[pd index]] dimension using a [[pd series]] or a [[pd column]]
```python
series1 > 2
# a False 
# b False 
# c True 
# d True

pd_df1["col1"] > 2
# a False 
# b False 
# c True 
# d True
```

2) a boolean mask on the [[pd column]] dimension of a [[pd dataframe]]
```python
pd_df1.loc["c"] > 4
# col1 False 
# col2 True 
# col3 True
```

3) a boolean mask in the shape of the complete [[pd dataframe]]
```python
pd_df1 > 6
#   col1 col2 col3 
# a False False True 
# b False False True 
# c False True True 
# d False True True
```


## Filtering based on a boolean mask
### filtering a [[pd series]]
```python
series1[series1 > 2]
# c 3 
# d 4
```
### filtering a [[pd dataframe]]
→ when a boolean masks with the same shape as the [[pd dataframe]] is used every value with False on its position will become NaN
```python
pd_df1[pd_df1 > 6]
#   col1 col2 col3 
# a NaN NaN 9 
# b NaN NaN 10 
# c NaN 7   11 
# d NaN 8   12
```
→ using a [[pd series]]  on the [[pd index]] dimension: every row with False on its [[pd index]] will be removed completely
```python
pd_df1[series1 > 2]
#    col1 col2 col3 
# c   3   7   11 
# d   4   8   12
```
→ using a [[pd series]]  on the [[pd column]] dimension: every [[pd column]] with False will be removed completely
```python
pd_df1.loc[:, pd_df1.loc["c"] > 4]
#   col2 col3 
# a   5   9 
# b   6   10 
# c   7   11 
# d   8   12
```


# Anki
START
Basic
pandas: boolean mask 
- create boolean maskes
- filter based on boolean masks
- on single dimensions of both
Back: 
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

## creating a boolean mask 
### using a [[pd series]]
1) a boolean mask on the [[pd index]] dimension using a [[pd series]] or a [[pd column]]
```python
series1 > 2
# a False 
# b False 
# c True 
# d True

pd_df1["col1"] > 2
# a False 
# b False 
# c True 
# d True
```

2) a boolean mask on the [[pd column]] dimension of a [[pd dataframe]]
```python
pd_df1.loc["c"] > 4
# col1 False 
# col2 True 
# col3 True
```

3) a boolean mask in the shape of the complete [[pd dataframe]]
```python
pd_df1 > 6
#   col1 col2 col3 
# a False False True 
# b False False True 
# c False True True 
# d False True True
```


## Filtering based on a boolean mask
### filtering a [[pd series]]
```python
series1[series1 > 2]
# c 3 
# d 4
```
### filtering a [[pd dataframe]]
→ when a boolean masks with the same shape as the [[pd dataframe]] is used every value with False on its position will become NaN
```python
pd_df1[pd_df1 > 6]
#   col1 col2 col3 
# a NaN NaN 9 
# b NaN NaN 10 
# c NaN 7   11 
# d NaN 8   12
```
→ using a [[pd series]]  on the [[pd index]] dimension: every row with False on its [[pd index]] will be removed completely
```python
pd_df1[series1 > 2]
#    col1 col2 col3 
# c   3   7   11 
# d   4   8   12
```
→ using a [[pd series]]  on the [[pd column]] dimension: every [[pd column]] with False will be removed completely
```python
pd_df1.loc[:, pd_df1.loc["c"] > 4]
#   col2 col3 
# a   5   9 
# b   6   10 
# c   7   11 
# d   8   12
```
Tags: code, pandas
<!--ID: 1668010184532-->
END