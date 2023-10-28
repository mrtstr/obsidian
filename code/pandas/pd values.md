- Attribute of [[pd dataframe]] or a [[pd series]]
- containing the data as a [[np ndarray]]
- [[pd index]] and [[pd column]] is mapping the labels to the dimensions of the values [[np ndarray]]
- can be accessed and manipulated using [[pd dataframe|dataframe]].values / [[pd series]].values

## example
![[pd dataframe#example df]]

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

# anki

START
Basic
pandas dataframe underlaying data storage (with example):

Back: 
- Attribute of [[pd dataframe]] or a [[pd series]]
- containing the data as a [[np ndarray]]
- [[pd index]] and [[pd column]] is mapping the labels to the dimensions of the values [[np ndarray]]
- can be accessed and manipulated using [[pd dataframe|dataframe]].values / [[pd series]].values
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
Tags: code pandas
<!--ID: 1668010184520-->
END