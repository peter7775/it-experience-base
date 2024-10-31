## What is a User Group in Linux

In Linux, different users have different roles or responsibilities. Some users might need the ability to execute applications, while others are restricted from accessing specific files and folders.

Groups let you create categories of users with pre-set permissions. Instead of managing permissions for each user account, you can simply add a user to a group to grant the appropriate permissions.

### Primary Group

The primary group is set to the logged-in user. Any files the user creates are automatically added to that group. A user can only belong to one primary group at a time. A primary group with the same name as the user is created, and any files created by the user are included in that group.

### Secondary Groups

A user can belong to any number of secondary groups (including none). Secondary groups are created to manage individual files and software applications. Members of the group inherit the read, write, and execute privileges for that group.
How to Create a User Group

To create a new group, enter the following:

`sudo groupadd new_group`

Replace new_group with the name you want for your new group.

create a user group in linux

## How to Add User to Group

### Add an Existing User to an Existing Group

Use the adduser command to add a user to a group:

`sudo adduser user_name new_group`

add existing user to an existing group

Use the useradd command to add a user:

`sudo useradd –G new_group user_name`

You can also use the usermod command to add a user to a group:

`sudo usermod –a –G group_name user_name`

The usermod command uses the –append and –group options to append the user to a particular group. Without using –append, the user could be dropped from other groups.

### Add a User to Multiple Groups at Once

Use the usermod command to specify multiple groups to add to:

`sudo usermod –a –G new_group,new_group2,new_group3 user_name`

### Create a User and Add to Group

This is useful for creating a new user on the fly for a specific software application. Enter the following:

`sudo useradd –G new_group new_user`

Next, assign a password to the new user:

`sudo passwd new_user`

### Change a Users Primary Group

All previous commands have been used to manage the secondary groups a user belongs to. In most cases, a user’s primary group is the same as their username.

To change a users primary group, enter the command:

`sudo usermod –g new_group user_name`

The lower-case –g specifies the primary group. (Upper-case –G refers to a secondary group.) A user can only have one primary group, so the old primary group user_name won’t be primary anymore for this user.

## How to Remove a User From a Group

The gpasswd tool is used for managing groups. To remove a user from a group:

`sudo gpasswd –d user_name new_group`

Note: The gpasswd tool can also be used for other administrative tasks such as defining group administrators and setting a password for access to group resources. Use the man gpasswd command for details.

### Delete a Group

To delete a group, use the command:

`sudo groupdel new_group`

example of deleting a user group in linux

## How to List Groups in Linux

Linux comes with several different groups by default. Some of these, like the sudo group, can be used to grant permissions. Others are hidden, used for system tasks.

To view a list of groups on your system by displaying the /etc/groups file:

`sudo  vim /etc/groups`

fedora:
`cut -d: -f1 /etc/group`

To display the groups that a user belongs to with the groups command:

`groups`

#### find groups of logged-in user

The image above shows the groups that the logged-in user ‘sofija’ belongs to. You can display groups for a different user by specifying the username:

`groups other_user`

Another method to display the groups a user belongs to, including user ID (uid) and group ID (gid), is to use the id command:

`id user_name`

## Other Common Groups

There are a several common group names you might encounter in Linux:



|         |                                                                             |
| ------- | --------------------------------------------------------------------------- |
| sudo    | A member of this group can use the sudo command to elevate their privileges |
| wheel   | This is an older method of granting sudo-like privileges                    |
| cdrom   | Allows the user to mount the optical drive                                  |
| adm     | Allows the user to monitor Linux system logs                                |
| lpadmin | Allows the user to configure printers                                       |
| plugdev | Allows the user to access external storage devices                          |

    / ***Sofija Simic*** - https://phoenixnap.com/kb/how-to-add-user-to-group-linux /