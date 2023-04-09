- A [[pa Schema]] is a collection of named [[pa Field|pa Fields]]
![[pa Field]]
- each [[pa Field]] holding additional information of a [[pa Array]] and both togather are a column
- similar to a [[pa Struct]]
```python
fields = [
    pa.field('s0', pa.int32()),
    pa.field('s1', pa.string()),
    pa.field('s2', pa.string()),
    pa.field('s3', pa.int32()),
]

my_schema1 = pa.schema(fields)
my_schemastruct2 = pa.schema(    # sorter
   [
	   ('s0', pa.int32()), ('s1', pa.string()), 
	   ('s2', pa.string()), ('s3', pa.int32())
   ]
)
```