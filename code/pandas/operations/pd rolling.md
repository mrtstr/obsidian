```python
df = pd.DataFrame(
	{
		"A": range(6),
		"B": range(6,12),
	}
)
```
| | A | B | 
|---:|----:|----:| 
| 0 | 0 | 6 | 
| 1 | 1 | 7 | 
| 2 | 2 | 8 | 
| 3 | 3 | 9 | 
| 4 | 4 | 10 | 
| 5 | 5 | 11 |

```python
(
	df
	.assign(A_shifted=df["A"].shift(-1))
	.assign(
		rolling_sum_centered=df["A"]
		.rolling(3, center=True, min_periods=1)
		.sum()
	)
	.assign(
		rolling_sum_arbi=df["A"]
		.shift(-1)
		.rolling(3, min_periods=1)
		.sum()
	)
	.assign(
		window_in_list = pd.Series(
			[
				list(window)
				for window in list(df["A"].rolling(
						3, center=True, 
						min_periods=1
					)
				)
			]
		)
	)
)
```

| | A | B | A_shifted | rolling_sum_centered | rolling_sum_arbi | window_in_list | 
|---:|----:|----:|------------:|--------------:|---------------:|:-----------------| 
| 0 | 0 | 6 | 1 | 1 | 1 | [0, 1] | 
| 1 | 1 | 7 | 2 | 3 | 3 | [0, 1, 2] | 
| 2 | 2 | 8 | 3 | 6 | 6 | [1, 2, 3] | 
| 3 | 3 | 9 | 4 | 9 | 9 | [2, 3, 4] | 
| 4 | 4 | 10 | 5 | 12 | 12 | [3, 4, 5] | 
| 5 | 5 | 11 | nan | 9 | 9 | [4, 5] |



# anki


START
Basic
[[pandas]] [[pd rolling]] example: for [[pd Column]] `A` of the following [[pd DataFrame]]
- sum on a centered window of size 3 without nans
- sum on a window of size 3 with an arbitrary position without nans
- for each value: list of `[pre value, value, following value]`

| | A | B | 
|---:|----:|----:| 
| 0 | 0 | 6 | 
| 1 | 1 | 7 | 
| 2 | 2 | 8 | 
| 3 | 3 | 9 | 
| 4 | 4 | 10 | 
| 5 | 5 | 11 |

Back: 
```python
(
	df
	.assign(A_shifted=df["A"].shift(-1))
	.assign(
		rolling_sum_centered=df["A"]
		.rolling(3, center=True, min_periods=1)
		.sum()
	)
	.assign(
		rolling_sum_arbi=df["A"]
		.shift(-1)
		.rolling(3, min_periods=1)
		.sum()
	)
	.assign(
		window_in_list = pd.Series(
			[
				list(window)
				for window in list(df["A"].rolling(
						3, center=True, 
						min_periods=1
					)
				)
			]
		)
	)
)
```

| | A | B | A_shifted | rolling_sum_centered | rolling_sum_arbi | window_in_list | 
|---:|----:|----:|------------:|--------------:|---------------:|:-----------------| 
| 0 | 0 | 6 | 1 | 1 | 1 | [0, 1] | 
| 1 | 1 | 7 | 2 | 3 | 3 | [0, 1, 2] | 
| 2 | 2 | 8 | 3 | 6 | 6 | [1, 2, 3] | 
| 3 | 3 | 9 | 4 | 9 | 9 | [2, 3, 4] | 
| 4 | 4 | 10 | 5 | 12 | 12 | [3, 4, 5] | 
| 5 | 5 | 11 | nan | 9 | 9 | [4, 5] |


Tags: code, pandas

END

START
Basic
give the output.

```python
(
	df
	.assign(A_shifted=df["A"].shift(-1))
	.assign(
		rolling_sum_centered=df["A"]
		.rolling(3, center=True, min_periods=1)
		.sum()
	)
	.assign(
		rolling_sum_arbi=df["A"]
		.shift(-1)
		.rolling(3, min_periods=1)
		.sum()
	)
	.assign(
		window_in_list = pd.Series(
			[
				list(window)
				for window in list(df["A"].rolling(
						3, center=True, 
						min_periods=1
					)
				)
			]
		)
	)
)
```

| | A | B | 
|---:|----:|----:| 
| 0 | 0 | 6 | 
| 1 | 1 | 7 | 
| 2 | 2 | 8 | 
| 3 | 3 | 9 | 
| 4 | 4 | 10 | 
| 5 | 5 | 11 |

Back: 

| | A | B | A_shifted | rolling_sum_centered | rolling_sum_arbi | window_in_list | 
|---:|----:|----:|------------:|--------------:|---------------:|:-----------------| 
| 0 | 0 | 6 | 1 | 1 | 1 | [0, 1] | 
| 1 | 1 | 7 | 2 | 3 | 3 | [0, 1, 2] | 
| 2 | 2 | 8 | 3 | 6 | 6 | [1, 2, 3] | 
| 3 | 3 | 9 | 4 | 9 | 9 | [2, 3, 4] | 
| 4 | 4 | 10 | 5 | 12 | 12 | [3, 4, 5] | 
| 5 | 5 | 11 | nan | 9 | 9 | [4, 5] |

Tags: code, pandas

END