
![[li virtual memory#li virtual memory]]

## memory paging
- mapping [[li virtual memory]] to [[li physical memory (RAM)]] and adresses on [[li disc]] in a page table
- done in the [[li memory management unit]] of the [[li kernel]]
- efficient copying of data between [[li process|processes]] with copy on write
- pages from the [[li disc]] can be mapped to the [[li virtual memory]] space of a [[li process]] without physicly copying it
- when the [[li process]] wants to read a page that is not in the [[li physical memory (RAM)]] the fault handler will copy the pages from the [[li disc]] to the [[li physical memory (RAM)]]
- when the [[li physical memory (RAM)]] is full data can be copied from the [[li physical memory (RAM)]] to the [[li disc]] and adapt the page table accordingly without impact the [[li virtual memory]]

![[pageswaping.png]]
-   System libraries can be shared by mapping them into the virtual address space of more than one process.
-   Processes can also share virtual memory by mapping the same block of memory to more than one process.
-   Process pages can be shared during a fork( ) system call, eliminating the need to copy all of the pages of the original ( parent ) process.
- different page replacement strategies Basic Page Replacement,  FIFO Page Replacement,  Optimal Page Replacement, _**Least Recently Used**_, #### Second-Chance Algorithm
### page
- fixed-length contiguous block of [[li virtual memory]]
- size is determined by the architatue of the [[li cpu]]

### page frame
- smallest fixed-length contiguous block of [[li physical memory (RAM)]] 

### page table
A page table is a data structure that maps the [[li virtual memory]] addresses of pages to their physical locations in [[li memory]] or [[li disc]]


![[pagetabe.png]]

### page fault handler
if [[li virtual memory]] is accesses that is mapped to a page that is not in the [[li physical memory (RAM)]] and only on [[li disc]] the page fault handler
1) locates the page on [[li disc]]
2) brings the page into [[li physical memory (RAM)]] 
3) updates the page table accordingly.

![[1 yt13_erSJUJJuavgm_Wsnw.webp]]


### copy on write
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

START
Basic
[[li memory paging]]
- concept (6)
- components (2)
Back: 
## memory paging
- mapping [[li virtual memory]] to [[li physical memory (RAM)]] and adresses on [[li disc]] in a page table
- done in the [[li memory management unit]] of the [[li kernel]]
- efficient copying of data between [[li process|processes]] with copy on write
- pages from the [[li disc]] can be mapped to the [[li virtual memory]] space of a [[li process]] without physicly copying it
- when the [[li process]] wants to read a page that is not in the [[li physical memory (RAM)]] the fault handler will copy the pages from the [[li disc]] to the [[li physical memory (RAM)]]
- when the [[li physical memory (RAM)]] is full data can be copied from the [[li physical memory (RAM)]] to the [[li disc]] and adapt the page table accordingly without impact the [[li virtual memory]]


### page
- fixed-length contiguous block of [[li virtual memory]]
- size is determined by the architatue of the [[li cpu]]

### page frame
- smallest fixed-length contiguous block of [[li physical memory (RAM)]] 

### page table
A page table is a data structure that maps the [[li virtual memory]] addresses of pages to their physical locations in [[li memory]] or [[li disc]]

![[pagetabe 1.png]]


### page fault handler
if [[li virtual memory]] is accesses that is mapped to a page that is not in the [[li physical memory (RAM)]] and only on [[li disc]] the page fault handler
1) locates the page on [[li disc]]
2) brings the page into [[li physical memory (RAM)]] 
3) updates the page table accordingly.


![[1 yt13_erSJUJJuavgm_Wsnw 3.webp]]

### copy on write
- [[li memory management]] concept for sharing [[li physical memory (RAM)]] between [[li process|processes]] untill one of the involved [[li process]] performs a wirte operation
- a write operation the pysical memory will be copyed and changed
- only impacts the mapping between a [[li virtual memory]] andress and the [[li physical memory (RAM)]] adress
- from the process perspective its looks like each process has its own memory
- make [[li fork]] [[li syscall]] much more efficient


![[1 B3jzse_G1dIwL5US0LlStg 5.webp]]

Tags: code linux
<!--ID: 1701507903137-->
END

