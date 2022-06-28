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

  



