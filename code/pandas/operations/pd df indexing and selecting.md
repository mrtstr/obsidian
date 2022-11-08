![[pd dataframe#example df]]

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
## dot notation
rows and columns of [[pd dataframe]] and [[pd series]] can be selected using the dot notation instead of the dict notation
```python
pd_series.row_name == pd_series["row_name"]

pd_df.col_name == pd_series["col_name"]
```
# Anki
START
Basic
pandas DataFrames:
- 3 methods selecting columns
- 2 methods selecting rows
- how to select single rows/columns as DataFrame/Series
Back: 
### column
1) by name using the dict like syntax of DataFrames
2) by name using the second dimension of [[pd dataframe|DataFrame]].loc
3) by position using the second dimension of [[pd dataframe|DataFrame]].iloc
### row
1) by name using the first dimension of [[pd dataframe|DataFrame]].loc
2) by position using the first dimension of [[pd dataframe|DataFrame]].iloc
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
Tags: code, pandas
<!--ID: 1667921722423-->
END


START
Basic
pandas DataFrames:
- how to select columns and rows by name
- how to get:
1) slices
2) series
3) single column/row dataframes

Back: 
Using the loc function (when only complete columns are selected by name the dict syntax can be used):
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
Tags: code, pandas
<!--ID: 1667921722425-->
END


START
Basic
pandas DataFrames:
- how to select columns and rows by position
- how to get:
1) slices
2) series
3) single column/row dataframes

Back: 
Using the iloc function:
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
Tags: code, pandas
<!--ID: 1667921722427-->
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
Tags: code, pandas
<!--ID: 1667921722429-->
END
