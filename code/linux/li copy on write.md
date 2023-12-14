### [[li copy on write|copy on write]]
- [[li memory management]] concept for sharing [[li physical memory (RAM)]] between [[li process|processes]] untill one of the involved [[li process]] performs a wirte operation
- a write operation the pysical memory will be copyed and changed
- only impacts the mapping between a [[li virtual memory]] andress and the [[li physical memory (RAM)]] adress
- from the process perspective its looks like each process has its own memory
- make [[li fork]] [[li syscall]] much more efficient

![[1 B3jzse_G1dIwL5US0LlStg 1.webp]]


# anki

START
Basic
why does a [[li fork]] operation not cause onnessary memory copying? Expain the underlaying concept.
Back: 
## copy on write
- [[li memory management]] concept for sharing [[li physical memory (RAM)]] between [[li process|processes]] untill one of the involved [[li process]] performs a wirte operation
- a write operation the pysical memory will be copyed and changed
- only impacts the mapping between a [[li virtual memory]] andress and the [[li physical memory (RAM)]] adress
- from the process perspective its looks like each process has its own memory
- make [[li fork]] [[li syscall]] much more efficient

![[1 B3jzse_G1dIwL5US0LlStg 2.webp]]
Tags: code linux
<!--ID: 1701503639863-->
END