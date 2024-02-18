
## [[li FIFO special file]]
- also called named pipe
- unidirectional communication channel between [[li process|processes]] that is entered into the file system
- can be opend by any [[li process]] with a read or write [[li file descriptor]]
- can be created using the `mkfifo` [[li syscall]]
- usage is similar to a [[li ordinary pipe]] with the difference that a [[li FIFO special file]] is in the filessystem with an [[li ordinary pipe]] is opend togather with its [[li file descriptor|file descriptors]] which can only be passed to the [[li child process|child processes]] of the creating [[li process]]
- has to be opend simultaneously at both ends (read and write) before it can be used

![[li mkfifo#mkfifo(pathname)]]

## related
![[li file descriptor#li file descriptor]]
# anki

START
Basic
[[li FIFO special file]]
- concept
- how to create it
- how to use it
- differerence to a [[li ordinary pipe]]

Back: 
### [[li FIFO special file]]
- also called named pipe
- unidirectional communication channel between [[li process|processes]] that is entered into the file system
- can be opend by any [[li process]] with a read or write [[li file descriptor]]
- can be created using the `mkfifo` [[li syscall]]
- usage is similar to a [[li ordinary pipe]] with the difference that a [[li FIFO special file]] is in the filessystem with an [[li ordinary pipe]] is opend togather with its [[li file descriptor|file descriptors]] which can only be passed to the [[li child process|child processes]] of the creating [[li process]]
- has to be opend simultaneously at both ends (read and write) before it can be used


![[li mkfifo#mkfifo(pathname)]]

#### [[li file descriptor]]
- [[li file descriptor]] unique identifier for any kind of data stream
	- `CHR`: character special file(special part of the file system e.g. for a device or [[li standard streams]]) 
	- `DIR`: opend directory
	- `unix`: unix domain socket ([[li unix domain socket]])
	- `REG`: regular [[li file|file]]
	- `IPv4/IPv6`: internet domain socket [[network socket]]
	- `FIFO`: [[li FIFO special file]]
→ same interface 
- opening modes:
	- `r`: read only
	- `w`: write only
	- `u`: read and write
- index (small integer) to an entry in the [[li process]] table of open [[li file descriptor|file descriptors]]
Tags: code linux
<!--ID: 1708245724873-->
END