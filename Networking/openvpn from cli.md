## set
```
sudo cp /usr/share/doc/openvpn/contrib/pull-resolv-conf/client.{up,down} /etc/openvpn/

sudo chmod +x /etc/openvpn/client.{up,down}

sudo sed -i.e. 's|\bresolvconf\b|ignore-&|' /etc/openvpn/client.{up,down}
```

## start

```
sudo openvpn --config /[path to file]/my_expressvpn_[server location].ovpn --script-security 2 --up /etc/openvpn/client.up --down /etc/openvpn/client.down
```

* * * 
Ray Walsh / https://proprivacy.com/blog/openvpn-linux 
* * *