## uncomplicated Firewall (ufw)

`sudo ufw allow 4000`
## firewalld (CentoOS)

`firewall-cmd --add-port===4000==/tcp`
## iptables

`iptables -A INPUT -p tcp --dport ==4000== -j ACCEPT`
## test port for connection

`ls | nc -l -p 4000`

`telnet localhost 4000`

----
### source
https://www.digitalocean.com/community/tutorials/opening-a-port-on-linux