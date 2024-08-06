### Find the service name use
`service --status-all`
### Use it to start a service. Does not persist after reboot
`systemctl start service` 
### Use it to stop a service. Does not persist after reboot
`systemctl stop service` 
### Use it to restart a service
`systemctl restart service` 
### Shows the status of a service. Tells whether a service is currently running.
`systemctl status service` 
### Turns the service on, on the next reboot or on the next start event. It persists after reboot.
`systemctl enable service` 
### Turns the service off on the next reboot or on the next stop event. It persists after reboot.
`systemctl disable service` 