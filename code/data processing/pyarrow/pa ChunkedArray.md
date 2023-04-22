- Container for one or more [[pa Array|pa Arrays]] of the same [[pa datatype]]
- used to store the columns of a [[pa Table]] that consist of multiple [[pa RecordBatch|pa RecordBatchs]] and each of them is represented by chunk
- is not logically contiguous (like a linked list of [[pa Array|pa Arrays]] representing [[pa Buffer|pa Buffers]])
	→ can be concatenated [[zero copy]]


# anki

START
Basic
[[pa ChunkedArray]]: concepe and memory organisation
Back: 
- Container for one or more [[pa Array|pa Arrays]] of the same [[pa datatype]]
- used to store the columns of a [[pa Table]] that consist of multiple [[pa RecordBatch|pa RecordBatchs]] and each of them is represented by chunk
- is not logically contiguous (like a linked list of [[pa Array|pa Arrays]] representing [[pa Buffer|pa Buffers]])
	→ can be concatenated [[zero copy]]
Tags: code pyarrow
<!--ID: 1682152090756-->
END