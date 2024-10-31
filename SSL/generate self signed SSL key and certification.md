`openssl req -newkey rsa:3072 -new -x509 -days 3652 -nodes -out /etc/apache2/config/ssl/server.crt -keyout /etc/apache2/config/ssl/server.pem -subj "/CN=$SERVER_NAME"`

### certificate and key in one file

`openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout fullchain.pem -out fullchain.pem`


---
### source
https://www.digitalocean.com/community/tutorials/how-to-create-a-self-signed-ssl-certificate-for-apache-in-debian-10

https://medium.com/@tshenolomos/secure-apache-with-ssl-in-docker-9efd86329129