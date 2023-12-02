combination of [[li fork]] and [[li exec]] is often used creating and child [[li process]] that is executing something

In the kernel, fork is actually implemented by a `clone` system call. This `clone` interfaces effectively provides a level of abstraction in how the Linux kernel can create processes.

`clone` allows you to explicitly specify which parts of the new process are copied into the new process, and which parts are shared between the two processes. This may seem a bit strange at first, but allows us to easily implement _threads_ with one very simple interface.

![[li fork#li fork fork]]

![[li exec#li exec exec]]