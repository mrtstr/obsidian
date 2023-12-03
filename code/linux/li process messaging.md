-   Message passing systems must support at a minimum system calls for "send message" and "receive message".
-   A communication link must be established between the cooperating processes before messages can be sent.
-   There are three key issues to be resolved in message passing systems as further explored in the next three subsections:
    -   Direct or indirect communication ( naming )
    -   Synchronous or asynchronous communication
    -   Automatic or explicit buffering.

##### 3.4.2.1 Naming

-   With **direct communication** the sender must know the name of the receiver to which it wishes to send a message.
    -   There is a one-to-one link between every sender-receiver pair.
    -   For **symmetric** communication, the receiver must also know the specific name of the sender from which it wishes to receive messages.  
        For **asymmetric** communications, this is not necessary.
-   **Indirect communication** uses shared mailboxes, or ports.
    -   Multiple processes can share the same mailbox or boxes.
    -   Only one process can read any given message in a mailbox. Initially the process that creates the mailbox is the owner, and is the only one allowed to read mail in the mailbox, although this privilege may be transferred.
        -   ( Of course the process that reads the message can immediately turn around and place an identical message back in the box for someone else to read, but that may put it at the back end of a queue of messages. )
    -   The OS must provide system calls to create and delete mailboxes, and to send and receive messages to/from mailboxes.

##### 3.4.2.2 Synchronization

-   Either the sending or receiving of messages ( or neither or both ) may be either **blocking** or **non-blocking**.

##### 3.4.2.3 Buffering

-   Messages are passed via queues, which may have one of three capacity configurations:
    1.  **Zero capacity** - Messages cannot be stored in the queue, so senders must block until receivers accept the messages.
    2.  **Bounded capacity**- There is a certain pre-determined finite capacity in the queue. Senders must block if the queue is full, until space becomes available in the queue, but may be either blocking or non-blocking otherwise.
    3.  **Unbounded capacity** - The queue has a theoretical infinite capacity, so senders are never forced to block.