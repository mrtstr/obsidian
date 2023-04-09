- Attribute of [[pandas]] [[pd dataframe|dataframes]] and [[pd series|series]]
- can be interpreted as labels of rows (axis 0)
- equivalent to the [[pd column]] but on the other axis
- is saved inside a wrapped [[np ndarray]] (like [[pd column]])
- can have multiple levels: [[pd multiindex]]
- can be accessed and manipulated:
```python
# wrapper read only:
print(pd_df1.index)
# Index(['a', 'b', 'c', 'd'], dtype='object')
print(type(pd_df1.index))
# <class 'pandas.core.indexes.base.Index'>

# underlaying data: can be manipulated
print(pd_df1.index.values)
# ['a' 'b' 'c' 'd']
print(type(pd_df1.index.values))
# <class 'numpy.ndarray'>
```
- can be overwritten
```python
pd_df1.index = ["e", "b", "d", "f"]
```
- [[pd index]] can be reset: reset_index will replace the index with counting
```python
pd_df1.reset_index(drop=False)  # default: convert the index to a row
pd_df1.reset_index(drop=True)  # completly remove the index
```
# anki

START
Basic
pandas index:
- concept
- how to access it
- how to manipulate it
- how to reset it
Back: 
- Attribute of [[pandas]] [[pd dataframe|dataframes]] and [[pd series|series]]
- can be interpreted as labels of rows
- is saved inside a wrapped [[np ndarray]]
- can be accessed and manipulated:
```python
# wrapper read only:
print(pd_df1.index)
# Index(['a', 'b', 'c', 'd'], dtype='object')
print(type(pd_df1.index))
# <class 'pandas.core.indexes.base.Index'>

# underlaying data: can be manipulated
print(pd_df1.index.values)
# ['a' 'b' 'c' 'd']
print(type(pd_df1.index.values))
# <class 'numpy.ndarray'>
```
- can be overwritten
```python
pd_df1.index = ["e", "b", "d", "f"]
```
- [[pd index]] can be reset: reset_index will replace the index with counting
```python
pd_df1.reset_index(drop=False)  # default: convert the index to a row
pd_df1.reset_index(drop=True)  # completly remove the index
```
Tags: code, pandas
<!--ID: 1668010184538-->
END

