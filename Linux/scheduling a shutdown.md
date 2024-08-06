#### Scheduling a shutdown

To shutdown run the command:

`sudo shutdown -P +60`

That will wait 60 mins before starting the shutdown sequence.

You could do:

`sudo shutdown -P 1:00`

to shutdown at 1 AM and

`sudo shutdown -P now`

to shutdown now.

A message is broadcast to all terminals to warn about the shutdown.

#### Cancel a pending shutdown

After, starting a shutdown, if the time argument is not "+0" or "now", you can use:

`sudo shutdown -c` 
* * *

/ ***Tim*** https://askubuntu.com/questions/505929/shutdown-after-a-certain-time / 