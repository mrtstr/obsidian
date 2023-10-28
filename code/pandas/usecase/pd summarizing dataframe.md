## Metadata: [[pd dataframe|DataFrame]].info()
Showing info about the [[pd dataframe|dataframes]]:
- [[pd index]] properties
- [[pd column]] properties
- [[pd dtype]]
- memory usage
## Data Summary: [[pd dataframe|DataFrame]].describe()
showing statistical information about the data inside the [[pd dataframe]]
- number of rows
- mean
- minimum/maximum
- some quantiles
```python
pd_df1.describe()
# col1 col2 col3 
# count 4.000000 4.000000 4.000000 
# mean 2.500000 6.500000 10.500000 
# std 1.290994 1.290994 1.290994 
# min 1.000000 5.000000 9.000000 
# 25% 1.750000 5.750000 9.750000 
# 50% 2.500000 6.500000 10.500000 
# 75% 3.250000 7.250000 11.250000 
# max 4.000000 8.000000 12.000000
```
### memory usage summary: [[pd dataframe|DataFrame]].memory_usage(deep=True)
memory usage for each column in byte
```python
pd_df1.memory_usage(deep=True)
# Index 232 
# col1 32 
# col2 32 
# col3 32 
```
# anki

START
Basic
[[pandas]]: 
- summarize [[pd dataframe]] (3)
Back: 
## Metadata: [[pd dataframe|DataFrame]].info()
Showing info about the [[pd dataframe|dataframes]]:
- [[pd index]] properties
- [[pd column]] properties
- [[pd dtype]]
- memory usage
## Data Summary: [[pd dataframe|DataFrame]].describe()
showing statistical information about the data inside the [[pd dataframe]]
- number of rows
- mean
- minimum/maximum
- some quantiles
```python
pd_df1.describe()
# col1 col2 col3 
# count 4.000000 4.000000 4.000000 
# mean 2.500000 6.500000 10.500000 
# std 1.290994 1.290994 1.290994 
# min 1.000000 5.000000 9.000000 
# 25% 1.750000 5.750000 9.750000 
# 50% 2.500000 6.500000 10.500000 
# 75% 3.250000 7.250000 11.250000 
# max 4.000000 8.000000 12.000000
```
### memory usage summary: [[pd dataframe|DataFrame]].memory_usage(deep=True)
memory usage for each column in byte
```python
pd_df1.memory_usage(deep=True)
# Index 232 
# col1 32 
# col2 32 
# col3 32 
```
Tags: code pandas
<!--ID: 1667921722406-->
END