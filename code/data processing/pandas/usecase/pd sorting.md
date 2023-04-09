![[pd dataframe#example df]]

## sort after values
### sort [[pd index]]
- sort: sort_values command on axis 1 (rows)
```python
pd_df1.sort_values(["col1", "col2"],ascending=False, axis=0)
#   col1 col2 col3 
# d  4    8   12 
# c  3    7   11 
# b  2    6   10 
# a  1    5   9
```
### sort [[pd column]]
- sort: sort_values command on axis 0 (columns)
```python
pd_df1.sort_values(["a", "b"],ascending=False, axis=1)
#   col3 col2 col1 
# a   9   5   1 
# b   10  6   2 
# c   11  7   3 
# d   12  8   4
```

## sort after [[pd index]]/[[pd column]] names
### sort [[pd index]]
- sort: sort_index command on axis 1 (rows)
```python
pd_df1.sort_values(ascending=False, axis=0)
#   col1 col2 col3 
# d  4    8   12 
# c  3    7   11 
# b  2    6   10 
# a  1    5   9
```
### sort [[pd column]]
- sort: sort_index command on axis 0 (columns)
```python
pd_df1.sort_index(ascending=False, axis=1)
#   col3 col2 col1 
# a   9   5   1 
# b   10  6   2 
# c   11  7   3 
# d   12  8   4
```
### sort after [[pd multiindex]]
```python
print(mi_df.sort_index(axis=0, level=["X", "Y"]))
#        A        B 
# X Y 
# 1 blue 0.437798 0.821285 
#   red  0.888439 0.589792 
# 2 blue 0.940415 0.289277 
# 1 red  0.154805 0.841461
print(mi_df.sort_index(axis=0, level=["Y", "X"]))
#        A         B 
# X  Y 
# 1 blue 0.437798 0.821285 
# 2 blue 0.940415 0.289277 
# 1 red  0.888439 0.589792 
# 2 red  0.154805 0.841461
```
# anki

START
Basic
[[pandas]]: sorting
- after values
- [[pd column]] / [[pd index]] (with example)
- after [[pd multiindex]]
Back: 
## sort after values
### sort [[pd index]]
- sort: sort_values command on axis 1 (rows)
```python
pd_df1.sort_values(["col1", "col2"],ascending=False, axis=0)
#   col1 col2 col3 
# d  4    8   12 
# c  3    7   11 
# b  2    6   10 
# a  1    5   9
```
### sort [[pd column]]
- sort: sort_values command on axis 0 (columns)
```python
pd_df1.sort_values(["a", "b"],ascending=False, axis=1)
#   col3 col2 col1 
# a   9   5   1 
# b   10  6   2 
# c   11  7   3 
# d   12  8   4
```

## sort after [[pd index]]/[[pd column]] names
### sort [[pd index]]
- sort: sort_index command on axis 1 (rows)
```python
pd_df1.sort_values(ascending=False, axis=0)
#   col1 col2 col3 
# d  4    8   12 
# c  3    7   11 
# b  2    6   10 
# a  1    5   9
```
### sort [[pd column]]
- sort: sort_index command on axis 0 (columns)
```python
pd_df1.sort_index(ascending=False, axis=1)
#   col3 col2 col1 
# a   9   5   1 
# b   10  6   2 
# c   11  7   3 
# d   12  8   4
```
### sort after [[pd multiindex]]
```python
print(mi_df.sort_index(axis=0, level=["X", "Y"]))
#        A        B 
# X Y 
# 1 blue 0.437798 0.821285 
#   red  0.888439 0.589792 
# 2 blue 0.940415 0.289277 
# 1 red  0.154805 0.841461
print(mi_df.sort_index(axis=0, level=["Y", "X"]))
#        A         B 
# X  Y 
# 1 blue 0.437798 0.821285 
# 2 blue 0.940415 0.289277 
# 1 red  0.888439 0.589792 
# 2 red  0.154805 0.841461
```
Tags: code, pandas
<!--ID: 1668010184528-->
END