### list of running services

`sudo systemctl list-jobs`

### determine your current system manager

use the “pstree” command and to check the first process ever run on your system

`pstree | head -n 5`

### List Services using systemctl

`systemctl list-units --type=service`

### List All Services on Linux using list-units

`systemctl list-units --type=service --all`

### List Services By State

```
systemctl list-units --state=<state>

systemctl list-units --state=<state1>,<state2>
```

“state” can be one of the following values : **active**, **inactive**, **activating**, **deactivating**, **failed**, **not-found** or dead

### List All Service Files using list-unit-files

Finally, if you are interested in “loaded“, “installed“, “disabled” as well as “enabled” service files, there is a another command that might be pretty handy.

`systemctl list-unit-files --type=service`

Alternatively, you can use the “grep” command in order to search for specific paths on your system that may contain service files.

`ls -l /etc/systemd/system /usr/lib/systemd/service | egrep .service$`


/ Author schkn  https://devconnected.com/how-to-list-services-on-linux/#comment-23006 /