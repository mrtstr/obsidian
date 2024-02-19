### [[li file descriptor]]
- [[li file descriptor]] unique identifier for any kind of data stream
	- `CHR`: character special file(special part of the file system e.g. for a device or [[li standard streams]]) 
	- `DIR`: opend directory
	- `unix`: unix domain socket ([[li unix domain socket]])
	- `REG`: regular [[li file|file]]
	- `IPv4/IPv6`: internet domain socket [[li network socket]]
	- `FIFO`: [[li FIFO special file]]
→ same interface 
- opening modes:
	- `r`: read only
	- `w`: write only
	- `u`: read and write
- index (small integer) to an entry in the [[li process]] table of open [[li file descriptor|file descriptors]]

### [[li syscall|systemcalls]] for working with [[li file descriptor|file descriptors]]

![[li open#li open]]

![[li close#li close]]

![[li seek#li seek (fd, offset, whence)]]

![[li read#li read (count, buff)]]

![[li write#li write (count, buff)]]


### displaying of [[li file descriptor|file descriptors]]
![[li lsof#`lsof`]]

# anki
START
Basic
[[li file descriptor]]
- concept
- types (6)
- opening modes (3)
- how to display them
Back: 
### [[li file descriptor]]
- [[li file descriptor]] unique identifier for any kind of data stream
	- `CHR`: character special file(special part of the file system e.g. for a device or [[li standard streams]]) 
	- `DIR`: opend directory
	- `unix`: unix domain socket ([[li unix domain socket]])
	- `REG`: regular [[li file|file]]
	- `IPv4/IPv6`: internet domain socket [[li network socket]]
	- `FIFO`: [[li FIFO special file]]
→ same interface 
- opening modes:
	- `r`: read only
	- `w`: write only
	- `u`: read and write
- index (small integer) to an entry in the [[li process]] table of open [[li file descriptor|file descriptors]]


### `lsof`
[[shell command]] `lsof` list all open [[li file descriptor|file descriptors]] 
```bash
lsof  # list all open file descriptors
	[-p PID]     # only open files of a specific process
	[-P]         # show used ports
	[-i [:port]]     # show only network file descriptors (and optionally filter for port)
	[-n]     # show ip adress instead of host name
```

```bash
lsof <path of file>  
# list all processes that have currently opened the given file
```

### provided information

#### `FD`: more information about the file descriptor
- `cwd` - current working directory
- `txt` - binary file
- `mem` - memory mapped file
- integer number for [[li standard streams]] and open [[li file|files]]
- opening mode: (`r` for read access, `w` for write access, `u` for read and write access)


Tags: code linux
<!--ID: 1707667667223-->
END



START
Basic
[[li file descriptor]]
- concept
- types (6)
- opening modes(3)
- [[li syscall|systemcalls]] for working with [[li file descriptor|file descriptors]] (5)
Back: 
### [[li file descriptor]]
- [[li file descriptor]] unique identifier for any kind of data stream
	- `CHR`: character special file(special part of the file system e.g. for a device or [[li standard streams]]) 
	- `DIR`: opend directory
	- `unix`: unix domain socket ([[li unix domain socket]])
	- `REG`: regular [[li file|file]]
	- `IPv4/IPv6`: internet domain socket [[li network socket]]
	- `FIFO`: [[li FIFO special file]]
→ same interface 
- opening modes:
	- `r`: read only
	- `w`: write only
	- `u`: read and write
- index (small integer) to an entry in the [[li process]] table of open [[li file descriptor|file descriptors]]



### [[li open]]
- [[li syscall]] for opening a [[li file]] by pathname
- returns a [[li file descriptor]] to access the data

### [[li close]]
- [[li syscall]] for closing a [[li file descriptor]]

### [[li seek]](fd, offset, whence)
- [[li syscall]] for changing the position in a [[li file descriptor]]
- for supported for all [[li file descriptor]] (only when random access possible)
- modes
	1) file offset is set to offset
	2) file offset is incremented by offset
	3) offset is set to the file end plus offset

### [[li read]](count, buff)
- [[li syscall]] for reading `count` bytes from a [[li file descriptor]] and writing it to the [[li virtual memory]] starting at adress `buff`

### [[li write]](count, buff)
- [[li syscall]] for writing `count` bytes to a [[li file descriptor]] from the [[li virtual memory]] starting at adress `buff`



Tags: code linux
<!--ID: 1707667667225-->
END