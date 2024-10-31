`openssl genrsa -out "server.key" 3072`
`openssl req -newkey rsa:2048 -nodes -keyout server.key -out server.csr -subj "/C=CZ/ST=Prague/L=Prague/O=Global Security/OU=IT Department/CN=excon.cz"`
`openssl x509 -signkey server.key -in server.csr -req -days 365 -out server.crt`
`openssl req -x509 -sha256 -days 1825 -nodes -newkey rsa:2048 -keyout rootCA.key -out rootCA.crt  -subj "/C=CZ/ST=Prague/L=Prague/O=Global Security/OU=IT Department/CN=excon.cz"`
`openssl x509 -req -CA rootCA.crt -CAkey rootCA.key -in server.csr -out server.crt -days 365 -CAcreateserial -extfile server.ext`

### configuration file (server.ext)

`authorityKeyIdentifier=keyid,issuer`  
`basicConstraints=CA:FALSE`  
`subjectAltName = @alt_names`  
`[alt_names]`  
`DNS.1 = domain (ex.attabik.id)`

----
### source

https://helloattabik.medium.com/sys-admin-create-a-self-signed-certificate-with-openssl-on-linux-debian-10-11-f2e6d95d12cd