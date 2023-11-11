### CPU time
- on the [[li scheduling and CPU time|scheduling]] of the [[li kernel]]
	- **TIME+:** Total CPU time consumed by the process.
	- **%CPU**: Percentage of CPU used by the process.

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

## 5 scheduling policies
1. **SCHED_OTHER**: the standard round-robin time-sharing policy  
2. **SCHED_BATCH**: for “batch” style execution of processes  
3. **SCHED_IDLE**: for running very low priority background jobs.  
4. **SCHED_FIFO**: a first-in, first-out policy  
5. **SCHED_RR**: a round-robin policy

normal scheduling policies (1 to 3) and the real time scheduling policies (4 and 5)

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