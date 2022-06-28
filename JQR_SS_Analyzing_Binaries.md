# JQR
JQR Notes 

SS - Socket Statistics

Analyze a linux binary to determine the following:
  - Purpose of binary 
  - Functions of binary
  - Kernel Modules used
  - External connections and/or attempts to connect
  - Files utilized/written to
cle
The purpose of the ss (socket statistics) is used to show network statistics.
SS is essential for gathering network information and troubleshooting network issues.

The output returns a list of open non-listening sockets with established connections.
  - Netid – Type of socket. Common types are TCP, UDP, u_str (Unix stream), and u_seq (Unix sequence).
  - State – State of the socket. Most commonly ESTAB (established), UNCONN (unconnected), LISTEN (listening).
  - Recv-Q – Number of received packets in the queue.
  - Send-Q – Number of sent packets in the queue.
  - Local address:port – Address of local machine and port.
  - Peer address:port – Address of remote machine and port.


![image](https://user-images.githubusercontent.com/105453604/176179741-f733eba3-1c54-4a77-ae0e-c211892ff53e.png)

In the STATE colunm
  - UDP is usually left blank
  - TCP could be one of the following
    - LISTEN: Server-side only. The socket is waiting for a connection request.
    - SYN-SENT: Client-side only. This socket has made a connection request and is waiting to see if it’s accepted.
    - SYN-RECEIVED: Server-side only. This socket is waiting for a connection acknowledgment after accepting a connection request.
    - ESTABLISHED: Server and clients. A working connection has been established between the server and the client, allowing data to be transferred between the two.
    - FIN-WAIT-1: Server and clients. This socket is awaiting a connection termination request from the remote socket, or an acknowledgment of a connection termination request that was previously sent from this socket.
    - FIN-WAIT-2: Server and clients. This socket is awaiting a connection termination request from the remote socket.
    - CLOSE-WAIT: Server and client. This socket is awaiting a connection termination request from the local user.
    - CLOSING: Server and clients. This socket is awaiting a connection termination request acknowledgment from the remote socket.
    - LAST-ACK: Server and client. This socket is awaiting an acknowledgment of the connection termination request it sent to the remote socket.
    - TIME-WAIT: Server and clients. This socket sent an acknowledgment to the remote socket to let it know it received the remote socket’s termination request. It’s now waiting to make sure that acknowledgment was received.
    - CLOSED: There is no connection, so the socket has been terminated.
    

How ss is setup and what it can display
  - ss [options] [ FILTER ]
  - when no options options are used ss displays a list of open non-listening sockets that have an established connection.
  - ss -t -a 
    - Displays all TCP socket
  - ss -t -l -Z
    - This Displays only listening sockets with process SELinux security contexts.
      - [ss -tlZ.txt](https://github.com/PigPotato100/JQR/files/9001366/ss.-tlZ.txt)
      
This command filters connections by port number.
  - ss -at '( dport = :22 or sport = :22 )'
    ![image](https://user-images.githubusercontent.com/105453604/176196760-d6ddc9ac-2140-4664-aa1e-4fef887d6605.png)
    


