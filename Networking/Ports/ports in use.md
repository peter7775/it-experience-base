### Popular port numbers in Linux



|            |            |
| ---------- | ---------- |
| HTTP       | TCP 80     |
| HTTPS      | TCP 443    |
| POP3       | TCP 110    |
| SMTP       | TCP 25     |
| SSH        | TCP 22     |
| DNS/DOMAIN | TCP/UDP 53 |

    Use the cat command or grep command/egrep command to query port numbers as follows:

```
cat /etc/services
grep -w 80 /etc/services
egrep -w '53/(tcp|udp)' /etc/services
```

### How to check if a port is in use on Linux

The procedure is as follows:

Open the terminal application on Linux.
Type any one of the following command to check if a port is in use on Linux
```
sudo lsof -i -P -n | grep LISTEN
sudo netstat -tulpn | grep LISTEN
sudo netstat -tulpn | grep :443
sudo ss -tulpn | grep LISTEN
sudo ss -tulpn | grep ':22'
```

Search for the TCP or UDP port description in /etc/services file on Linux:
```
grep -E -w 'PORT_NUMBER_HERE/(tcp|udp)' /etc/services
```

### How can you find out which process is listening on a port on Linux

Type the ss command or netstat command to see if a TCP port 443 is in use on Linux?

```
sudo netstat -tulpn | grep :443
sudo ss -tulpn | grep :443
```

The port 443 is in use and opened by nginx service. Where,



|  switch   |                                                                                       |
| --- | ------------------------------------------------------------------------------------- |
| t  | Display TCP sockets/port                                                              |
| u  | Show UDP sockets/port                                                                 |
| l  | See only listening sockets i.e. open port                                             |
| p  | Also display process name that opened port/socket                                     |
| n  | View addresses and port numbers in numerical format. Do not use DNS to resolve names. |

    
### Getting a list of all open port in production

Simply run:

```
sudo lsof -i -P -n | grep LISTEN
sudo ss -tulpn
sudo netstat -tulpn
```
