- Element wise operations can be performed con [[pd dataframe]] and [[pd series]]
- element wise operations are slower than vectorised operations and should be avoided when possible
- usually done using [[py lambda functions]] or a defined function
- the functions [[pd map]] ([[pd series]] only), [[pd applymap]] ([[pd dataframe]] only) and [[pd apply]] (both) can be used
- [[pd map]] and [[pd applymap]] are for simple transformations whole [[pd apply]] is for more complex operations along an axis ([[pd index]]: 0 or [[pd column]]: 1) and reviel

## summary

![[IZys3.png]]

# example
![[pd dataframe#example df]]

## [[pd map]]/[[pd applymap]]
- gets single element and transforms it
```python
def double(x):
	if x > 2:
		return x * 2
	return 0
display(pd_df1["col1"].map(lambda x: x *2 if x > 2 else 0))
display(pd_df1["col1"].map(double))
# a   0
# b   0
# c   9
# d   16
display(pd_df1.applymap(lambda x: x *2 if x > 2 else 0))
display(pd_df1.applymap(double))
#  col1 col2 col3
# a 0   10   18 
# b 0   12   20 
# c 6   14   22 
# d 8   16   24
```
## [[pd apply]]
- get a [[pd series]] and performs a transformation on the [[pd series]]
- can de a reduction but does not have to
- can be performed on [[pd column]] or [[pd index]]
```python
pd_df1.apply(np.add.accumulate, axis=0) # with reduction on rows

#  col1 col2 col3
# a 1   5    9
# b 3   11   19
# c 6   18   30
# d 10  26   42

pd_df1.apply(np.add.accumulate, axis=1) # with reduction on columns

#  col1 col2 col3
# a 1   6    15
# b 2   8    18
# c 3   10   21
# d 4   12   24


pd_df1.apply(np.sum, axis=0) # without reduction on rows
# col1 10
# col2 26
# col3 42

pd_df1.apply(np.sum, axis=1) # without reduction on columns
# a 15
# b 18
# c 21
# d 24
```
# Anki
START
Basic
pandas applying functions element wise:
- simple mapping on [[pd series]]
- simple mapping on [[pd dataframe]]
- transformations with reduction ([[pd column]] and [[pd index]])
- transformations without reduction ([[pd column]] and [[pd index]])
Back: 
- Element wise operations can be performed con [[pd dataframe]] and [[pd series]]
- element wise operations are slower than vectorised operations and should be avoided when possible
- usually done using [[py lambda functions]] or a defined function
- the functions [[pd map]] ([[pd series]] only), [[pd applymap]] ([[pd dataframe]] only) and [[pd apply]] (both) can be used
- [[pd map]] and [[pd applymap]] are for simple transformations whole [[pd apply]] is for more complex operations along an axis ([[pd index]]: 0 or [[pd column]]: 1) and reviel

## summary

![[IZys3.png]]


## [[pd map]]/[[pd applymap]]
- gets single element and transforms it
```python
def double(x):
	if x > 2:
		return x * 2
	return 0
display(pd_df1["col1"].map(lambda x: x *2 if x > 2 else 0))
display(pd_df1["col1"].map(double))
# a   0
# b   0
# c   9
# d   16
display(pd_df1.applymap(lambda x: x *2 if x > 2 else 0))
display(pd_df1.applymap(double))
#  col1 col2 col3
# a 0   10   18 
# b 0   12   20 
# c 6   14   22 
# d 8   16   24
```
## [[pd apply]]
- get a [[pd series]] and performs a transformation on the [[pd series]]
- can de a reduction but does not have to
- can be performed on [[pd column]] or [[pd index]]
```python
pd_df1.apply(np.add.accumulate, axis=0) # with reduction on rows

#  col1 col2 col3
# a 1   5    9
# b 3   11   19
# c 6   18   30
# d 10  26   42

pd_df1.apply(np.add.accumulate, axis=1) # with reduction on columns

#  col1 col2 col3
# a 1   6    15
# b 2   8    18
# c 3   10   21
# d 4   12   24


pd_df1.apply(np.sum, axis=0) # without reduction on rows
# col1 10
# col2 26
# col3 42

pd_df1.apply(np.sum, axis=1) # without reduction on columns
# a 15
# b 18
# c 21
# d 24
```

Tags: code, pandas
<!--ID: 1668090818833-->
END


START
Basic
[[pandas]] [[pd apply]]:
- concept and examples
Back: 
## [[pd apply]]
- get a [[pd series]] and performs a transformation on the [[pd series]]
- can de a reduction but does not have to
- can be performed on [[pd column]] or [[pd index]]
```python
pd_df1.apply(np.add.accumulate, axis=0) # with reduction on rows

#  col1 col2 col3
# a 1   5    9
# b 3   11   19
# c 6   18   30
# d 10  26   42

pd_df1.apply(np.add.accumulate, axis=1) # with reduction on columns

#  col1 col2 col3
# a 1   6    15
# b 2   8    18
# c 3   10   21
# d 4   12   24


pd_df1.apply(np.sum, axis=0) # without reduction on rows
# col1 10
# col2 26
# col3 42

pd_df1.apply(np.sum, axis=1) # without reduction on columns
# a 15
# b 18
# c 21
# d 24
```

Tags: code, pandas
<!--ID: 1668090818835-->
END


START
Basic
[[pandas]] [[pd map]]/[[pd applymap]]:
- concept and examples
Back: 
## [[pd apply]]
- get a [[pd series]] and performs a transformation on the [[pd series]]
- can de a reduction but does not have to
- can be performed on [[pd column]] or [[pd index]]
```python
pd_df1.apply(np.add.accumulate, axis=0) # with reduction on rows

#  col1 col2 col3
# a 1   5    9
# b 3   11   19
# c 6   18   30
# d 10  26   42

pd_df1.apply(np.add.accumulate, axis=1) # with reduction on columns

#  col1 col2 col3
# a 1   6    15
# b 2   8    18
# c 3   10   21
# d 4   12   24


pd_df1.apply(np.sum, axis=0) # without reduction on rows
# col1 10
# col2 26
# col3 42

pd_df1.apply(np.sum, axis=1) # without reduction on columns
# a 15
# b 18
# c 21
# d 24
```
Tags: code, pandas
<!--ID: 1668090818837-->
END