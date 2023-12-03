## `renice`
Change the niceness values of a user (regular) [[li process]] or a group of user processes
`renice [value] -p [pids]` e.g.  `renice 5 -p 2 10` (change nicesness of process with pids 2 and 10 to 5)
`renice [value] -u [user]` e.g.  `renice -20 -u user1` (change the niceness of all processes of user1 to -20)

![[li scheduling#niceness (NI)]]