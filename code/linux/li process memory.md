
### memory
1) data space of each process (own stack space, used for local variables)
2) shared memory area (read only for save sharing)
3) memory adress space

- **VIRT**: virtual memory
	- Size of the processes adress space
	- e.g. process memory-maps a large file, the file is actually stored on disk, but it still takes up "address space" in the process.
- **RES**: resident memory
	- amount of physical memory used by a process.
- **SHR**: Amount of memory shared with other processes.
- **%MEM**; Percentage of RAM used by the process.

