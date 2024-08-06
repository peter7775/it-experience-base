# status and disable

### Check SELinux Status
`sestatus` 

### Set SELinux in Permissive Mode (Temporary)
`sudo setenforce 0` 
`sudo setenforce Permissive` 

### Set SELinux in Permissive Mode (Permanent)

edit: /etc/selinux/config 
`SELINUX=permissive`

### Permanently Disable SELinux on Fedora
edit: /etc/selinux/config 
`SELINUX=disabled`

https://tecadmin.net/how-to-disable-selinux-on-fedora/


