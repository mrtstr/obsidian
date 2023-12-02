syscalls - Linux system calls
The system call is the fundamental interface between an application and the Linux kernel.
System calls are generally not invoked directly, but rather via wrapper functions in [[li glibc]]

A system call is just a userspace request of a kernel service.
When your program wants to write to or read from a file,
start to listen for connections on a [socket](https://en.wikipedia.org/wiki/Network_socket),
delete or create directory
In other words, a system call is just a [C](https://en.wikipedia.org/wiki/C_%28programming_language%29) kernel space function that user space programs call to handle some request.

linux kernel around 350

![[li fork#li fork fork]]

![[li exec#li exec exec]]

![[li wait#li wait wait]]


![[li exit#li exit exit]]
