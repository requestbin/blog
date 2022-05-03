SSH is the default administrative protocol on linux. SSH tunneling and SSH port forwarding are very useful features for the lateral movement phrase.
There are three types of SSH port forwarding:
* Local Port Forwarding. - Forwards a connection from the client host to the SSH server host and then to the destination host port.
* Remote Port Forwarding. - Forwards a port from the server host to the client host and then to the destination host port.
* Dynamic Port Forwarding. - Creates a SOCKS proxy server that allows communication across a range of ports.
This article try to note all commands to use when needed

# Local Port Forwarding
![ảnh](https://user-images.githubusercontent.com/10446854/166500357-01120258-0a28-40a7-9423-1d497d3ed579.png)

```
ssh -L [LOCAL_IP:]LOCAL_PORT:DESTINATION:DESTINATION_PORT [USER@]SSH_SERVER
```
The options used are as follows:
* ```[LOCAL_IP:]LOCAL_PORT``` - The local machine IP address and port number. When LOCAL_IP is omitted, the ssh client binds on the localhost.
* ```DESTINATION:DESTINATION_PORT``` - The IP or hostname and the port of the destination machine.
* ```[USER@]SERVER_IP``` - The remote SSH user and server IP address.

Example:
```
ssh -L 3336:db001.host:3306 user@pub001.host
```

# Remote Port Forwarding
```
ssh -R [REMOTE:]REMOTE_PORT:DESTINATION:DESTINATION_PORT [USER@]SSH_SERVER
```
The options used are as follows:
* ```[REMOTE:]REMOTE_PORT``` - The IP and the port number on the remote SSH server. An empty REMOTE means that the remote SSH server will bind on all interfaces.
* ```DESTINATION:DESTINATION_PORT``` - The IP or hostname and the port of the destination machine.
* ```[USER@]SERVER_IP``` - The remote SSH user and server IP address.

Example:
```
ssh -R 0.0.0.0:10521:10.0.0.1:1521 user@10.0.0.1 #Remote port 1521 accessible in port 10521 from everywhere
```

# Dynamic Port Forwarding
```
ssh -D [LOCAL_IP:]LOCAL_PORT [USER@]SSH_SERVER
```
The options used are as follows:
* ```[LOCAL_IP:]LOCAL_PORT``` - The local machine IP address and port number. When LOCAL_IP is omitted, the ssh client binds on localhost.
* ```[USER@]SERVER_IP``` - The remote SSH user and server IP address.

Example:
```
ssh -D 3128 -N -f user@remote.host
```
