- [[pd series]] and [[pd index]] and [[pd column]] of [[pd dataframe]] can be filtered with a [[py lambda functions]] and the [[pd loc]] function
- the [[py lambda functions]] gets the [[pd dataframe]] as input and has to return a [[pd series]] like object containing the selected [[pd column]] (when axis 1) or the [[pd index]] when (axis 0)

![[pd dataframe#example df]]

```python
pd_df1.loc[lambda pd_df1: pd_df1["col1"] > 2]
  
#  col1 col2 col3
# b   2   6   10
# c   3   7   11
# d   4   8   12
pd_df1.loc[:, lambda pd_df1: pd_df1.loc["a"] > 2]
  
#  col2 col3
# a   5   9
# b   6   10
# c   7   11
# d   8   12

pd_df1.loc[:, lambda pd_df1: ["col2", "col3"]]
#  col2 col3
# a   5   9
# b   6   10
# c   7   11
# d   8   12


pd_df1.loc[lambda pd_df1: list("bcd")]
#  col2 col3
# a   5   9
# b   6   10
# c   7   11
# d   8   12
```


START
Basic
pandas [[pd column]] and [[pd index]] selection by callable
Back: 
- [[pd series]] and [[pd index]] and [[pd column]] of [[pd dataframe]] can be filtered with a [[py lambda functions]] and the [[pd loc]] function
- the [[py lambda functions]] gets the [[pd dataframe]] as input and has to return a [[pd series]] like object containing the selected [[pd column]] (when axis 1) or the [[pd index]] when (axis 0)

```python
pd_df1.loc[lambda pd_df1: pd_df1["col1"] > 2]
  
#  col1 col2 col3
# b   2   6   10
# c   3   7   11
# d   4   8   12
pd_df1.loc[:, lambda pd_df1: pd_df1.loc["a"] > 2]
  
#  col2 col3
# a   5   9
# b   6   10
# c   7   11
# d   8   12

pd_df1.loc[:, lambda pd_df1: ["col2", "col3"]]
#  col2 col3
# a   5   9
# b   6   10
# c   7   11
# d   8   12


pd_df1.loc[lambda pd_df1: list("bcd")]
#  col2 col3
# a   5   9
# b   6   10
# c   7   11
# d   8   12
```
Tags: code, pandas
<!--ID: 1668090818840-->
END
