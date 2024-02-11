## scheduling


![[3_06_QueueingDiagram.jpg]]

### CPU time
- on the [[li scheduling|scheduling]] of the [[li kernel]]
	- **TIME+:** Total CPU time consumed by the process.
	- **%CPU**: Percentage of CPU used by the process.

### Context Switch
-   Whenever an interrupt arrives, the CPU must do a **state-save** of the currently running process, then switch into kernel mode to handle the interrupt, and then do a **state-restore** of the interrupted process.
-   Similarly, a **context switch** occurs when the time slice for one process has expired and a new process is to be loaded from the ready queue. This will be instigated by a timer interrupt, which will then cause the current process's state to be saved and the new process's state to be restored.
-   Saving and restoring states involves saving and restoring all of the registers and program counter(s), as well as the process control blocks described above.
-   Context switching happens VERY VERY frequently, and the overhead of doing the switching is just lost CPU time, so context switches ( state saves & restores ) need to be as fast as possible. Some hardware has special provisions for speeding this up, such as a single machine instruction for saving or restoring all registers at once.
-   Some Sun hardware actually has multiple sets of registers, so the context switching can be speeded up by merely switching which set of registers are currently in use. Obviously there is a limit as to how many processes can be switched between in this manner, making it attractive to implement the medium-term scheduler to swap some processes out as shown in Figure 3.8 above.
![[3_07_QueuingDiagram2.jpg]]

### 5 scheduling policies
1. **SCHED_OTHER**: the standard round-robin time-sharing policy  
2. **SCHED_BATCH**: for “batch” style execution of processes  
3. **SCHED_IDLE**: for running very low priority background jobs.  
4. **SCHED_FIFO**: a first-in, first-out policy  
5. **SCHED_RR**: a round-robin policy

normal scheduling policies (1 to 3) and the real time scheduling policies (4 and 5)

## priority

#### (overall) priority level (PR)
- numer in range (-100 to 39) 
- the lower the **PR** the higher the priority
- **direct** impact on the scheduling (CPU time)
- can only be directly changes with [[li root]] rights and is usually stet automaticity by the [[li kernel]]

#### niceness (NI)
- used to derrive the **priority level (PR)** of normal user processes
- numer in range (-20 to 19) that can be set by a non [[li root]] user to influence the priority of the process
- hight niceness leads to a low priority

#### normal user [[li process]]
- PR is derrives from the niceness: `PR = 20 + NI` (→ `PR` in range (0 to 39)

#### real time [[li process]]
- e.g. kernel’s tasks
- PR scheduling with a different policy
- PR in a range -100 to -1
- is calculated based of the round robin priority `PR = -1-rr_prior`



# Anki

START
Basic
[[linux]] scheduling priority 
- two concepts 
- 2 different kinds of [[li process]]
- (and how they are related)
Back: 
### (overall) priority level (PR)
- numer in range (-100 to 39) 
- the lower the **PR** the higher the priority
- **direct** impact on the scheduling (CPU time)
- can only be directly changes with [[li root]] rights and is usually stet automaticity by the [[li kernel]]

### niceness (NI)
- used to derrive the **priority level (PR)** of normal user processes
- numer in range (-20 to 19) that can be set by a non [[li root]] user to influence the priority of the process
- hight niceness leads to a low priority

### normal user [[li process]]
- PR is derrives from the niceness: `PR = 20 + NI` (→ `PR` in range (0 to 39)

### real time [[li process]]
- e.g. kernel’s tasks
- PR scheduling with a different policy
- PR in a range -100 to -1
- is calculated based of the round robin priority `PR = -1-rr_prior`

Tags: code linux
<!--ID: 1699690123156-->
END