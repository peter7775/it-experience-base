in **/etc/docker/daemon.json**

```
{
	"metrics-addr":	"0.0.0.0:9323",
	"experimental":	true
}
```

restart Docker service:
`systemctl restart docker`

metrics output is in adress:
`http://localhost:9323/metrics`