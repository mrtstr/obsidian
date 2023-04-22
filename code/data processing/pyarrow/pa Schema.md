## Schema
- collection of named [[pa Field|pa Fields]]
- defines structure of a [[pa RecordBatch]], [[pa Table]], [[pa RecordBatchReader]]
![[pa Field]]
- each [[pa Field]] holding additional information of a [[pa Array]] and both togather are a column
- similar to a [[pa StructType]]

```python
fields = [
	pa.field('id', pa.int32()),
	pa.field('first_name', pa.string()),
	pa.field('last_name', pa.string()),
]
schema1 = pa.schema(fields)
schema1 = pa.schema(    # shorter
   [
	   ('id', pa.int32()), 
	   ('first_name', pa.string()), 
	   ('last_name', pa.string()), ('s3', pa.string())
   ]
)
```

# anki

START
Basic
- [[pa Schema]] and relationship to [[pa Field]]
- example: create a [[pa Schema]] for a [[pa RecordBatch]] containing the id, the first and last name of persons
Back: 
# Schema
- collection of named [[pa Field|pa Fields]] (placeholder for data with `name`, `type`, and if its ``nullable)
- defines structure of a [[pa RecordBatch]], [[pa Table]], [[pa RecordBatchReader]]


## example
```python
fields = [
	pa.field('id', pa.int32()),
	pa.field('first_name', pa.string()),
	pa.field('last_name', pa.string()),
]
schema1 = pa.schema(fields)
schema1 = pa.schema(    # shorter
   [
	   ('id', pa.int32()), 
	   ('first_name', pa.string()), 
	   ('last_name', pa.string()), ('s3', pa.string())
   ]
)
```

Tags: code pyarrow
<!--ID: 1681116775350-->
END