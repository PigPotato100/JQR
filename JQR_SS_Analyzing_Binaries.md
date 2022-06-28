# JQR
JQR Notes 

SS - Socket Statistics

Analyze a linux binary to determine the following:
  - Purpose of binary 
  - Functions of binary
  - Kernel Modules used
  - External connections and/or attempts to connect
  - Files utilized/written to

The purpose of the ss (socket statistics) is used to show network statistics.
SS is essential for gathering network information and troubleshooting network issues.

The output returns a list of open non-listening sockets with established connections.
  Netid – Type of socket. Common types are TCP, UDP, u_str (Unix stream), and u_seq (Unix sequence).
  State – State of the socket. Most commonly ESTAB (established), UNCONN (unconnected), LISTEN (listening).
  Recv-Q – Number of received packets in the queue.
  Send-Q – Number of sent packets in the queue.
  Local address:port – Address of local machine and port.
  Peer address:port – Address of remote machine and port.


