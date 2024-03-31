### bind (syscall)
- [[li syscall]] for binding an adress (path or [[port]]) to and existing [[li socket]]
- while the [[server]] uses [[li bind]] to bind a adress to a [[li socket]] the [[client]] uses [[li connect]] to connect to the adress
- [[li unix domain socket]]: the adress is a filesystem path
- [[li internet domain socket]]: adress is a [[port]]
```C
int bind(
	sockfd, // file descriptor for the socket
	sockadd, // adress (path or port) to bind to the file descriptor
) // -> return code
```


# anki

START
Basic
what does the [[li syscall]] [[li bind]] do?
what kind of adress is used?
Back: 
### bind (syscall)
- [[li syscall]] for binding an adress (path or [[port]]) to and existing [[li socket]]
- while the [[server]] uses [[li bind]] to bind a adress to a [[li socket]] the [[client]] uses [[li connect]] to connect to the adress
- [[li unix domain socket]]: the adress is a filesystem path
- [[li internet domain socket]]: adress is a [[port]]
```C
int bind(
	sockfd, // file descriptor for the socket
	sockadd, // adress (path or port) to bind to the file descriptor
) // -> return code
```

Tags: code linux
<!--ID: 1711869568837-->
END