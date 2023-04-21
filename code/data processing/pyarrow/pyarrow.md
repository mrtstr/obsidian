## concept
- library providing columnar data structures for in-memory computing
- can handle large datasets by partitioning of data in smaller chunks
- base data representation of [[polars]] and [[pandas]] 2.0
- Arrow can be used with [[parquet]], [[pandas]], [[polars]], [[pyspark]]
![[Screenshot from 2023-04-09 20-11-37.png]]


Basically, a Table in PyArrow/Arrow C++ isn't really the data itself, but rather a container consisting of pointers to data. How it works is:

-   A Buffer represents an actual, singular allocation. In other words, Buffers are contiguous, full stop. They may be mutable or immutable.
-   An Array contains 0+ Buffers and imposes some sort of semantics into them. (For instance, an array of integers, or an array of strings.) Arrays are "contiguous" in the sense that each buffer is contiguous, and conceptually the "column" is not "split" across multiple buffers. (This gets really fuzzy with nested arrays: a struct array does split its data across multiple buffers, in some sense! I need to come up with a better wording of this, and will contribute this to upstream docs. But I hope what I mean here is reasonably clear.)
-   A ChunkedArray contains 0+ Arrays. A ChunkedArray is not logically contiguous. It's kinda like a linked list of chunks of data. Two ChunkedArrays can be concatenated "zero copy", i.e. the _underlying buffers_ will not get copied.
-   A Table contains 0+ ChunkedArrays. A Table is a 2D data structure (both columns and rows).
-   A RecordBatch contains 0+ Arrays. A RecordBatch is also a 2D data structure.

Hence, you can concantenate two Tables "zero copy" with `pyarrow.concat_tables`, by just copying pointers. But you cannot concatenate two RecordBatches "zero copy", because you have to concatenate the Arrays, and then you have to copy data out of buffers.


## datastructures
[[pa Field]]
- placeholder for data: holds [[pa datatype]] and additional properties of values 
[[pa Schema]]: 
- collection of named [[pa Field|pa Fields]]
- defines structure of a [[pa RecordBatch]], [[pa Table]], [[pa RecordBatchReader]]
[[pa Array]]
- immutable collection of data of the same [[pa datatype]]
[[pa RecordBatch]]
- collection of [[pa Array]] of the same length with a [[pa Schema]]
[[pa Table]]
- same properties as a [[pa RecordBatch]] but can contrain one or multiple [[pa RecordBatch|pa RecordBatchs]] of the same [[pa Schema]] that are logicly treated as one
# anki

START
Basic
[[pyarrow]]
- conecpt (4)
Back: 
## concept
- library providing columnar data structures for in-memory computing
- can handle large datasets by partitioning of data in smaller chunks
- base data representation of [[polars]] and [[pandas]] 2.0
- Arrow can be used with [[parquet]], [[pandas]], [[polars]], [[pyspark]]

![[Screenshot from 2023-04-09 20-11-37.png]]

Tags: code pyarrow
<!--ID: 1681037725709-->
END