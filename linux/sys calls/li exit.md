## [[li exit|exit]]
- [[li syscall]] that terminates the calling [[li process]] including all its threads imidiatly
- the [[li kernel]] releases all resources allocated to the calling [[li process]]
- open [[li file descriptor]] if the [[li process]] are closed
- any children of the process are inherited by the [[li process]] with the [[li process id]] 1 (usually the [[li init process]]) → [[li orphan process]]


# Anki

START
Basic
how can a [[li process]] call terminate itself?
what will happen with the [[li child process]]?
what happens to its [[li thread|threads]]?
Back: 
## [[li exit|exit]]
- [[li syscall]] that terminates the calling [[li process]] including all its threads imidiatly
- the [[li kernel]] releases all resources allocated to the calling [[li process]]
- open [[li file descriptor]] if the [[li process]] are closed
- any children of the process are inherited by the [[li process]] with the [[li process id]] 1 (usually the [[li init process]]) → [[li orphan process]]

Tags: code linux
<!--ID: 1702578315612-->
END