### basic command

`firefox`

### open

```
firefox https://linuxconfig.org
firefox -new-tab https://linuxconfig.org
firefox -new-window https://linuxconfig.org
```
### multiple tab

`firefox -url https://linuxconfig.org https://google.com`

### search

`firefox -search "linux tutorials"`

### private 

```
firefox -private
firefox -private-window https://linuxconfig.org
```

### kiosk-mode (without ui)

`firefox --kiosk https://linuxconfig.org`

### safe mode

`firefox -safe-mode`

### profile

```
firefox -ProfileManager
firefox -P "linuxconfig"
```
### clear cache files

`rm -rf ~/.cache/mozilla/firefox/*`

### clear browsing history

```
rm ~/.mozilla/firefox/*release/*.sqlite
OR
rm ~/.mozilla/firefox/*default/*.sqlite
```











