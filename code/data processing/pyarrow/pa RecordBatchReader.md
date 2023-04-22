# RecordBatchReader

- Base class for reading stream of [[pa RecordBatch|pa RecordBatches]]
	→ can be used to iterate over [[pa RecordBatch|pa RecordBatches]] 
- useful when data bigger than avaliable memory
- provides their common [[pa Schema]] without having to load any [[pa RecordBatch|pa RecordBatches]]

## example
```python
schema=pa.schema([('x', pa.int64())])
def iter_record_batches():   # create iterator over the batchrecord
	for _ in range(2):
		yield pa.RecordBatch.from_arrays(
			[pa.array([1, 2, 3])], 
			schema=schema
		)

reader = pa.RecordBatchReader.from_batches(
   schema, 
   iter_record_batches()
)

for batch in reader:   # iterate over batchrecords
	print(batch)
```

| | x | 
|---:|----:| 
| 0 | 1 | 
| 1 | 2 | 
| 2 | 3 | 

| | x | 
|---:|----:| 
| 0 | 1 | 
| 1 | 2 | 
| 2 | 3 |


# anki

START
Basic
[[pa RecordBatchReader]]
- concept and when to use it
- reationship to [[pa Schema]]

Back: 
## concept
- Base class for reading stream of [[pa RecordBatch|pa RecordBatches]]
	→ can be used to iterate over [[pa RecordBatch|pa RecordBatches]] 
- useful when data bigger than avaliable memory
- provides their common [[pa Schema]] without having to load any [[pa RecordBatch|pa RecordBatches]]

Tags: code pyarrow
<!--ID: 1681116775353-->
END