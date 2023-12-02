- **child process** is started by **parent process**
- When linux starts, it runs a single program, **init** with PID 1 (prime ancestor of all processes)
other system processes are started by **init** or by other processes started by **init**

own programs with the system calls **fork()**, **exec()**, and **wait()**.


As we already stated, processes are **managed by the Kernel** on Linux.

when you boot a Linux system, your Linux kernel is loaded into memory, it is given a virtual filesystem in the RAM (also called **initramfs**) and the initial commands are executed.


![[Process.png]]