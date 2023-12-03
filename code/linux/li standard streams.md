- [[li interprocess communication|interconnected]] input and output communication channels between a [[li process]] and its environment when it begins execution
- 3 [[li standard streams]] [[li stdin]], [[li stdout]] and [[li stderr]]


(0 - stdin), standard output (1 - stdout), and standard error (2 - stderr)

- When a command is executed via an interactive [shell](https://en.wikipedia.org/wiki/Shell_(computing) "Shell (computing)"), the streams are typically connected to the [text terminal](https://en.wikipedia.org/wiki/Text_terminal "Text terminal") on which the shell is running, 
- can be changed with [[li redirection]] or a [[li ordinary pipe]]
- a [[li child process]] inherits the standard streams of its [[[li parent process]]

![[309px-Stdstreams-notitle.svg.png]]

![[li stdin]]

![[li stdout]]

![[li stderr]]