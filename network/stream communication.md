### [[stream communication]]
- sequenced
- reliable
- two-way full-duplex
- connection-based 
- asymetric ([[server]]/[[client]])
- e.g. [[transmission control protocol (TCP)]]


# rest
you say hello to each other (SYN/ACK in TCP), and then you exchange information. Once you are done, you say goodbye (FIN/ACK in TCP)

There is a guarantee that data will not arrive in a different order than you sent it, and there is a reasonable guarantee that data will not be damaged.

So you use a stream socket when having information in order and intact is important. File transfer protocols are a good example here.


Streambasierte Protokolle wie z. B. das TCP-Protokoll sind Streaming-Protokolle mit Sequencing und Fehlerkontrolle.