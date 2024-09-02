What is TCP? TCP or Transmission Control Protocol is a that provides reliable, ordered, and error checked delivery of a stream of bytes.

What is TCP? TCP or Transmission Control Protocol is a that provides reliable, ordered, and error checked delivery of a stream of bytes

A TCP connection is always in 1 of many different states. The list is the following:
1. **LISTEN**: A server socket is waiting for incoming connection requests. This state is only relevant for the server side of a connection.
2. **SYN-SENT**: A client socket is actively trying to establish a connection by sending a SYN (synchronize) packet. This state is only seen on the client side after it initiates a connection request.
3. **SYN-RECEIVED**: A socket is in this state when it has received a SYN packet from a client and sent back a SYN-ACK packet, but has not yet received an ACK in return. This state is typically seen on the server side during the connection establishment phase.
4. **ESTABLISHED**: The connection is fully established, and both sides can send and receive data. This is the normal state for an open connection where data transfer can occur.
5. **FIN-WAIT-1**: A socket is in this state when it has initiated an active close by sending a FIN (finish) packet to the other side, indicating it has finished sending data.
6. **FIN-WAIT-2**: A socket moves to this state after receiving an ACK for its FIN packet, indicating that the other side has acknowledged the close request but may still be sending data.
7. **CLOSE-WAIT**: A socket is in this state when it has received a FIN packet from the other side, indicating the other side wants to close the connection. The socket is waiting for the application to acknowledge this by sending its own FIN packet.
8. **CLOSING**: Both sides have sent FIN packets, but neither side has received the final ACK from the other. This state is rare and occurs when both sides simultaneously attempt to close the connection.
9. **LAST-ACK**: A socket is in this state after it has sent its FIN packet and is waiting for an ACK of that FIN from the other side. This is the final step before moving to the CLOSED state.
10. **TIME-WAIT**: A socket enters this state after it has received the final ACK for its FIN packet. The socket stays in this state for a specified time (typically 2*MSL, where MSL is the maximum segment lifetime) to ensure that any delayed packets are properly handled. This prevents issues caused by delayed duplicate packets from previous connections.
11. **CLOSED**: The connection is fully closed, and no further communication is possible. This state indicates that the connection has been terminated, and all resources associated with it have been released.*