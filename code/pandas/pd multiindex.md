- [[pandas]] [[pd dataframe]] and [[pd series]] can have an [[pd index]] with a higher multiple values for each row
- a [[pd dataframe]] [[pd column]] can have a [[pd multiindex]]
- the names of each index level is saved under pd_df.index.names
- the number of index dimensions (levels) are saved under pd_df.index.nlevels
## example multiindex df
```python
mi = pd.MultiIndex(
	levels = [[1, 2], ['red', 'blue']],
	codes=[[1,0,1,0], [1,1,0,0]]
)

mi_df = pd.DataFrame(
	data=np.random.random(size=(4,2)), 
	index=mi, columns=list("AB")
)
mi_df

#         A       B 
# 2 blue 0.287763 0.703470 
# 1 blue 0.941584 0.308614 
# 2 red  0.462107 0.264613 
# 1 red  0.279638 0.321357
```
## data storage and access
- the data is stored as a list of the unique elements on each level ([[pd multiindex|MultiIndex]].levels) plus mapping to the rows ([[pd multiindex|MultiIndex]].codes) -> [[pd categorical data]] encoding (memory efficient)
```python
mi = pd.MultiIndex(
	levels = [[1, 2], ['red', 'blue']],
	codes=[[1,0,1,0], [0,1,0,1]]
)

print(mi.codes)
# [[1, 0, 1, 0], [0, 1, 0, 1]]
print(mi.levels)
# [[1, 2], ['red', 'blue']]
```
- for a single level the complete index can be accessed using [[pd multiindex|MultiIndex]].get_level_values as a wrapped [[np ndarray]] with a single dimension (generated on the fly)
```python
print(mi.get_level_values(level=0))
# Int64Index([2, 1, 2, 1], dtype='int64')
print(mi.get_level_values(level=0).values)
# [2 1 2 1]
```
- data can also be returned as [[np ndarray]] containing [[py tuple]] ([[pd multiindex|MultiIndex]].values) (generated on the fly)
```python
print(mi.values)
# [(2, 'red') (1, 'blue') (2, 'red') (1, 'blue')]
```
## creating a [[pd multiindex]]
- standard constructor: taking a nested list like object and a code defining the positions
```python
mi = pd.MultiIndex(
	levels = [[1, 2], ['red', 'blue']],
	codes=[[1,0,1,0], [0,1,0,1]]
)

MultiIndex([(1, 'blue'),
        (2,  'red'),
        (1, 'blue'),
        (2,  'red')],
       )
```

- can be created from [[np ndarray]]
```python
pd.MultiIndex.from_arrays()
```
- can be created from the [[catesian product]] between single dimensional list like object
```python
pd.MultiIndex.from_product()
```
- from a [[pd dataframe]]
```python
pd.MultiIndex.from_frame()
```
## managing levels
```python
pd_df.index.set_levels()
pd_df.index.swaplevel()
pd_df.index.droplevel()

pd_df.index.reorder_levels()

pd_df.index.get_locs()
```


START
Basic
pandas [[pd multiindex]]: general concept
- what are they used for?
- basic attributes
Back: 
- [[pandas]] [[pd dataframe]] and [[pd series]] can have an [[pd index]] with a higher multiple values for each row
- a [[pd dataframe]] [[pd column]] can have a [[pd multiindex]]
- the names of each index level is saved under pd_df.index.names
- the number of index dimensions (levels) are saved under pd_df.index.nlevels

Tags: code pandas
<!--ID: 1668090818822-->
END


START
Basic
pandas [[pd multiindex]]: data storage and access:
- how are [[pd multiindex]] stored?
- how can the data be accessed?
Back: 
## data storage and access
- the data is stored as a list of the unique elements on each level ([[pd multiindex|MultiIndex]].levels) plus mapping to the rows ([[pd multiindex|MultiIndex]].codes) -> [[pd categorical data]] encoding (memory efficient)
```python
mi = pd.MultiIndex(
	levels = [[1, 2], ['red', 'blue']],
	codes=[[1,0,1,0], [0,1,0,1]]
)

print(mi.codes)
# [[1, 0, 1, 0], [0, 1, 0, 1]]
print(mi.levels)
# [[1, 2], ['red', 'blue']]
```
- for a single level the complete index can be accessed using [[pd multiindex|MultiIndex]].get_level_values as a wrapped [[np ndarray]] with a single dimension (generated on the fly)
```python
print(mi.get_level_values(level=0))
# Int64Index([2, 1, 2, 1], dtype='int64')
print(mi.get_level_values(level=0).values)
# [2 1 2 1]
```
- data can also be returned as [[np ndarray]] containing [[py tuple]] ([[pd multiindex|MultiIndex]].values) (generated on the fly)
```python
print(mi.values)
# [(2, 'red') (1, 'blue') (2, 'red') (1, 'blue')]
```
Tags: code pandas
<!--ID: 1668090818826-->
END


START
Basic
pandas [[pd multiindex]]: methods for creating a [[pd multiindex]] (4)
Back: 
## creating a [[pd multiindex]]
- standard constructor: taking a nested list like object and a code defining the positions
```python
mi = pd.MultiIndex(
	levels = [[1, 2], ['red', 'blue']],
	codes=[[1,0,1,0], [0,1,0,1]]
)

MultiIndex([(1, 'blue'),
        (2,  'red'),
        (1, 'blue'),
        (2,  'red')],
       )
```

- can be created from [[np ndarray]]
```python
pd.MultiIndex.from_arrays()
```
- can be created from the [[catesian product]] between single dimensional list like object
```python
pd.MultiIndex.from_product()
```
- from a [[pd dataframe]]
```python
pd.MultiIndex.from_frame()
```
Tags: code pandas
<!--ID: 1668090818828-->
END