### [[datagram]]
- connectionless
- unreliable (package loss and out of order)
- fixed length packages
- symetric
- e.g. [[user datagram protocol (UDP)]]
# rest
The basic unit of information, consisting of one or more data packets, which are passed across an Internet at the transport level.

A datagram socket is like passing a note in class. Consider the case where you are not directly next to the person you are passing the note to; the note will travel from person to person. It may not reach its destination, and it may be modified by the time it gets there. If you pass two notes to the same person, they may arrive in an order you didn't intend, since the route the notes take through the classroom may not be the same, one person might not pass a note as fast as another, etc.

You'd use a datagram socket when order is less important than timely delivery (think VoIP or game protocols)

Datagrammbasierte Protokolle wie z. B. UDP hingegen sind paketorientierte Protokolle und bieten kein Sequencing oder keine Fehlerkontrolle an