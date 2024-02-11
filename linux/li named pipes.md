
## [[li named pipes]]
-   Named pipes support bidirectional communication, communication between non parent-child related processes, and persistence after the [[li process]] which created them exits. Multiple processes can also share a named pipe, typically one reader and multiple writers.
-   In UNIX, named pipes are termed fifos, and appear as ordinary files in the file system.
    -   ( Recognizable by a "p" as the first character of a long listing, e.g. /dev/initctl )
    -   Created with mkfifo( ) and manipulated with read( ), write( ), open( ), close( ), etc.
    -   UNIX named pipes are bidirectional, but half-duplex, so two pipes are still typically used for bidirectional communications.
    -   UNIX named pipes still require that all processes be running on the same machine. Otherwise sockets are used.
-   Windows named pipes provide richer communications.
-   Full-duplex is supported.
-   Processes may reside on the same or different machines
-   Created and manipulated using CreateNamedPipe( ), ConnectNamedPipe( ), ReadFile( ),and WriteFile( ).