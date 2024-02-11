sharing memory between [[li process]]

-   In general the memory to be shared in a shared-memory system is initially within the address space of a particular process, which needs to make system calls in order to make that memory publicly available to one or more other processes.
-   Other processes which wish to use the shared memory must then make their own system calls to attach the shared memory area onto their address space.
-   Generally a few messages must be passed back and forth between the cooperating processes first in order to set up and coordinate the shared memory access.