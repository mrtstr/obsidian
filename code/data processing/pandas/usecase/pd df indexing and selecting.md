![[pd dataframe#example df]]

- Selecting columns using the dict syntax
```python
pd_df1["col1"]
# return Series of column with the name "col1"

pd_df1[["col1"]]
# return DataFrame containing only the column with the name "col1"

pd_df1[["col1", "col2"]]
# return Dataframe with a subset of columns (col1, col2)
```
- dot notation: rows and columns of [[pd dataframe]] and [[pd series]] can be selected using the dot notation instead of the dict notation
```python
pd_series.row_name == pd_series["row_name"]

pd_df.col_name == pd_series["col_name"]
```
- selecting rows and [[pd column]] and [[pd index]] by name using [[pd loc]]
- selecting rows and [[pd column]] and [[pd index]] by position using [[pd iloc]]
- selecting rows and [[pd column]] using [[pd boolean indexing]] and [[pd loc]]
- selecting [[pd index]] and [[pd column]] using [[py lambda functions]]: [[pd indexing by callable]]



# Anki
START
Basic
pandas DataFrames:
- 4 methods selecting columns
- 3 methods selecting rows
- how to select single rows/columns as DataFrame/Series
Back: 
### column
1) by name using the dict like syntax of DataFrames
2) by name using the second dimension of [[pd dataframe|DataFrame]].loc
3) by position using the second dimension of [[pd dataframe|DataFrame]].iloc
4) using a condition and a boolean mask [[pd series]] with an index on the column dimension in the second position of [[pd iloc]]
```python
pd_df1.loc[:, pd_df1.loc["c"] > 4]
#   col2 col3 
# a   5   9 
# b   6   10 
# c   7   11 
# d   8   12
```
### row
1) by name using the first dimension of [[pd dataframe|DataFrame]].loc
2) by position using the first dimension of [[pd dataframe|DataFrame]].iloc
3) using a condition and a boolean mask [[pd series]] with an index on the index dimension of the dataframe in the first position
```python
pd_df1[pd_df1["col1"] > 2]
#    col1 col2 col3 
# c   3   7   11 
# d   4   8   12
```
### series vs dataframe
- a series is return when a single column or row is selected except additional square brackets are used than a single row/column dataframe is returned

# examples
## selecting columns using the dict syntax
```python
pd_df1["col1"]
# return Series of column with the name "col1"

pd_df1[["col1"]]
# return DataFrame containing only the column with the name "col1"

pd_df1[["col1", "col2"]]
# return Dataframe with a subset of columns (col1, col2)
```

## selecting columns and rows by name

```python
pd_df1.loc["<row selection by name>", "<column selection by name>"]

pd_df1.loc["a"]
# returns a series containing the first row with index equal to column names

pd_df1.loc[["a"]]
# returns a DataFrame containing only one row 

pd_df1.loc[:, "col1"]
# returns a series containing the column with the name "col1"

pd_df1.loc[:, ["col1"]]
# returns a DataFrame containing with only the column with the name "col1"

pd_df1.loc[["a", "b"], ["col1", "col2"]]
# returns a DataFrame that has only the columns col1 and col2 and the rows a and b

pd_df1.loc["a":"b", "col1":"col2"]
# returns a DataFrame that has only the columns col1 and col2 and the rows a and b
```
## selecting columns and rows by position
```python
pd_df1.iloc["<row selection position>", "<column selection by position>"]

pd_df1.iloc[0]
# returns a series containing the first row with index equal to column names

pd_df1.iloc[[0]]
# returns a DataFrame containing only one row 

pd_df1.iloc[:, 0]
# returns a series containing the column with the name "col1"

pd_df1.iloc[:, [0]]
# returns a DataFrame containing with only the column with the name "col1"

pd_df1.iloc[[0, 1], [0, 1]]
# returns a DataFrame that has only the columns col1 and col2 and the rows a and b

pd_df1.iloc[0:1, 0:1]
# returns a DataFrame that has only the columns col1 and col2 and the rows a and b
```
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
Tags: code pandas
<!--ID: 1667921722423-->
END



START
Basic
pandas syntactic sugar for the dict syntax of [[pd dataframe]] and [[pd series]]
Back: 
## dot notation
rows and columns of [[pd dataframe]] and [[pd series]] can be selected using the dot notation instead of the dict notation
```python
pd_series.row_name == pd_series["row_name"]

pd_df.col_name == pd_series["col_name"]
```
Tags: code pandas
<!--ID: 1667921722429-->
END


START
Basic
pandas indexing: selecting [[pd column]] and/or [[pd index]] (6 without example)
Back: 
1) Selecting columns using the dict syntax
2) dot notation: rows and columns of [[pd dataframe]] and [[pd series]] can be selected using the dot notation instead of the dict notation
3) selecting rows and [[pd column]] and [[pd index]] by name using [[pd loc]]
4) selecting rows and [[pd column]] and [[pd index]] by position using [[pd iloc]]
5) selecting rows and [[pd column]] using [[pd boolean indexing]] and [[pd loc]]
6) selecting [[pd index]] and [[pd column]] using [[py lambda functions]]: [[pd indexing by callable]]

Tags: code pandas
<!--ID: 1668090818842-->
END
