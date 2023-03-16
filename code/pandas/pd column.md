![[pd DataFrame#example df]]

- attribute of a [[pd DataFrame]] 
- can be interpreted as the label of the column dimension (axis 1)
- equivalent to the [[pd Index]] but on the other axis 
- is saved inside a wrapped [[np ndarray]] (like [[pd Index]])
- can be accessed and manipulated:
```python
# wrapper read only:
print(pd_df1.columns)
# Index(['col1', 'col2', 'col3'], dtype='object')
print(type(pd_df1.columns))
# <class 'pandas.core.indexes.base.Index'>

# underlaying data: can be manipulated
print(pd_df1.columns.values)
# ['col1' 'col2' 'col3']
print(type(pd_df1.columns.values))
# <class 'numpy.ndarray'>
```

# anki

START
Basic
pandas columns:
- concept
- how to access it
- how to manipulate it
Back: 
- attribute of a [[pd DataFrame]] 
- can be interpreted as the label of the column dimension (axis 1)
- equivalent to the [[pd Index]] but on the other axis 
- is saved inside a wrapped [[np ndarray]] (like [[pd Index]])
- can be accessed and manipulated:
```python
# wrapper read only:
print(pd_df1.columns)
# Index(['col1', 'col2', 'col3'], dtype='object')
print(type(pd_df1.columns))
# <class 'pandas.core.indexes.base.Index'>

# underlaying data: can be manipulated
print(pd_df1.columns.values)
# ['col1' 'col2' 'col3']
print(type(pd_df1.columns.values))
# <class 'numpy.ndarray'>
```
Tags: code, pandas
<!--ID: 1668010184543-->
END