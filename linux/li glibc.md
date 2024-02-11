# What is glibc?

The GNU C Library project provides _the_ core libraries for the GNU system and GNU/Linux systems, as well as many other systems that use Linux as the kernel. These libraries provide critical APIs including ISO C11, POSIX.1-2008, BSD, OS-specific APIs and more. These APIs include such foundational facilities as open, read, write, malloc, printf, getaddrinfo, dlopen, pthread_create, crypt, login, exit and more.


Often the glibc wrapper function is quite thin, doing little work
other than copying arguments to the right registers before
invoking the system call, and then setting _[errno](https://man7.org/linux/man-pages/man3/errno.3.html)_ appropriately
after the system call has returned.  (These are the same steps
that are performed by [syscall(2)](https://man7.org/linux/man-pages/man2/syscall.2.html), which can be used to invoke
system calls for which no wrapper function is provided.)  Note:
system calls indicate a failure by returning a negative error
number to the caller on architectures without a separate error
register/flag, as noted in [syscall(2)](https://man7.org/linux/man-pages/man2/syscall.2.html); when this happens, the
wrapper function negates the returned error number (to make it
positive), copies it to _[errno](https://man7.org/linux/man-pages/man3/errno.3.html)_, and returns -1 to the caller of
the wrapper.