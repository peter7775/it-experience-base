### Install

`sudo dnf install kibana`
* * *
### Run Kibana with SysV init


Use the chkconfig command to configure Kibana to start automatically when the system boots up:

`sudo chkconfig --add kibana`

You can start and stop Kibana using the service command:

```
sudo -i service kibana start
sudo -i service kibana stop
```

If Kibana fails to start for any reason, it will print the reason for failure to STDOUT. Log files can be found in /var/log/kibana/.
* * *

### Run Kibana with systemd


To configure Kibana to start automatically when the system boots up, run the following commands:

```
sudo /bin/systemctl daemon-reload
sudo /bin/systemctl enable kibana.service
```

Kibana can be started and stopped as follows:

```
sudo systemctl start kibana.service
sudo systemctl stop kibana.service
```

These commands provide no feedback as to whether Kibana was started successfully or not. Log information can be accessed via journalctl -u kibana.service.


* * *
### Kibana port
`http://localhost:5601`