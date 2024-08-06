### The following commands will get you the IP address list to find **public IP addresse**s for your machine:

`curl ifconfig.me`
`curl -4/-6 icanhazip.com`
`curl ipinfo.io/ip`
`curl api.ipify.org`
`curl checkip.dyndns.org`
`dig +short myip.opendns.com @resolver1.opendns.com`
`host myip.opendns.com resolver1.opendns.com`
`curl ident.me`
`curl bot.whatismyipaddress.com`
`curl ipecho.net/plain`

### The following commands will get you the **private IP address** of your interfaces:

`ifconfig -a`
`ip addr (ip a)`
**`hostname -I | awk '{print $1}'`**
`ip route get 1.2.3.4 | awk '{print $7}'`
`(Fedora) Wifi-Settings→ click the setting icon next to the Wifi name that you are connected to → Ipv4 and Ipv6 both can be seen`
`nmcli -p device show`


/author: Archit Modi https://opensource.com/article/18/5/how-find-ip-address-linux /