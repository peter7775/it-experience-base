### [The quick and simple editor for cron schedule expressions - crontab.guru](https://crontab.guru/)

### Common (and uncommon) cron uses

I use the cron service to schedule obvious things, such as regular backups that occur daily at 2 a.m. I also use it for less obvious things.

The system times (i.e., the operating system time) on my many computers are set using the Network Time Protocol (NTP). While NTP sets the system time, it does not set the hardware time, which can drift. I use cron to set the hardware time based on the system time.

I also have a Bash program I run early every morning that creates a new "message of the day" (MOTD) on each computer. It contains information, such as disk usage, that should be current in order to be useful.

Many system processes and services, like Logwatch, logrotate, and Rootkit Hunter, use the cron service to schedule tasks and run programs every day.

The crond daemon is the background service that enables cron functionality.

The cron service checks for files in the /var/spool/cron and /etc/cron.d directories and the /etc/anacrontab file. The contents of these files define cron jobs that are to be run at various intervals. The individual user cron files are located in /var/spool/cron, and system services and applications generally add cron job files in the /etc/cron.d directory. The /etc/anacrontab is a special case that will be covered later in this article.



### Using crontab

The cron utility runs based on commands specified in a cron table (crontab). Each user, including root, can have a cron file. These files don't exist by default, but can be created in the /var/spool/cron directory using the crontab -e command that's also used to edit a cron file (see the script below). I strongly recommend that you not use a standard editor (such as Vi, Vim, Emacs, Nano, or any of the many other editors that are available). Using the crontab command not only allows you to edit the command, it also restarts the crond daemon when you save and exit the editor. 



```
# crontab -e
SHELL=/bin/bash
MAILTO=root@example.com
PATH=/bin:/sbin:/usr/bin:/usr/sbin:/usr/local/bin:/usr/local/sbin

# For details see man 4 crontabs

# Example of job definition:
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  * user-name  command to be executed

# backup using the rsbu program to the internal 4TB HDD and then 4TB external
01 01 * * * /usr/local/bin/rsbu -vbd1 ; /usr/local/bin/rsbu -vbd2

# Set the hardware clock to keep it in sync with the more accurate system clock
03 05 * * * /sbin/hwclock --systohc

# Perform monthly updates on the first of the month
# 25 04 1 * * /usr/bin/dnf -y update
```

The first three lines in the code above set up a default environment. The environment must be set to whatever is necessary for a given user because cron does not provide an environment of any kind. The SHELL variable specifies the shell to use when commands are executed. This example specifies the Bash shell. The MAILTO variable sets the email address where cron job results will be sent. These emails can provide the status of the cron job (backups, updates, etc.) and consist of the output you would see if you ran the program manually from the command line. The third line sets up the PATH for the environment. Even though the path is set here, I always prepend the fully qualified path to each executable.

`01 01 * * * /usr/local/bin/rsbu -vbd1 ; /usr/local/bin/rsbu -vbd2`

This line in my /etc/crontab runs a script that performs backups for my systems.





/ ***David Both***  - https://opensource.com/article/17/11/how-use-cron-linux /