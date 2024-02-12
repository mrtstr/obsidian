### [[li seek]](fd, offset, whence)
- [[li syscall]] for changing the position in a [[li file descriptor]]
- for supported for all [[li file descriptor]] (only when random access possible)
- modes
	1) `SEEK_SET`: file offset is set to offset
	2) `SEEK_CUR`: file offset is incremented by offset
	3) `SEEK_END`: offset is set to the file end plus offset