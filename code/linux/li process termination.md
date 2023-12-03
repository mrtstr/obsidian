[[li exit]] [[li syscall]] by their ownb
Processes may request their own termination by making the **exit( )** system call

Processes may also be terminated by the system for a variety of reasons, including:

-   The inability of the system to deliver necessary system resources.
-   In response to a KILL command, or other un handled process interrupt.
-   A parent may kill its children if the task assigned to them is no longer needed.
-   If the parent exits, the system may or may not allow the child to continue without a parent. ( On UNIX systems, orphaned processes are generally inherited by init, which then proceeds to kill them. The UNIX _**nohup**_ command allows a child to continue executing after its parent has exited. )

When a process terminates, all of its system resources are freed up, open files flushed and closed, etc. The process termination status and execution times are returned to the parent if the parent is waiting for the child to terminate, or eventually returned to init if the process becomes an orphan. ( Processes which are trying to terminate but which cannot because their parent is not waiting for them are termed **zombies**. These are eventually inherited by init as orphans and killed off. Note that modern UNIX shells do not produce as many orphans and zombies as older systems used to. )

![[li orphan process]]