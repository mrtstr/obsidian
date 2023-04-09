- A [[pa Struct]] is a collection of named [[pa Field|pa Fields]]
- similar to the [[pa Schema]] of a [[pa Table]]
- useful for creating nested data structures
```python
fields = [
    pa.field('s0', pa.int32()),
    pa.field('s1', pa.string()),
    pa.field('s2', pa.string()),
    pa.field('s3', pa.int32()),
]

my_struct1 = pa.struct(fields)
my_struct2 = pa.struct(    # sorter
   [
	   ('s0', pa.int32()), ('s1', pa.string()), 
	   ('s2', pa.string()), ('s3', pa.int32())
   ]
)
```