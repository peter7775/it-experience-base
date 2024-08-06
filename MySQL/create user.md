### How to Create a New User

`CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';`

`GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';`

`FLUSH PRIVILEGES;`


### How To Grant Different User Permissions


- ALL PRIVILEGES- as we saw previously, this would allow a MySQL user full access to a designated database (or if no database is selected, global access across the system)
- CREATE- allows them to create new tables or databases
- DROP- allows them to them to delete tables or databases
- DELETE- allows them to delete rows from tables
- INSERT- allows them to insert rows into tables
- SELECT- allows them to use the SELECT command to read through databases
- UPDATE- allow them to update table rows
- GRANT OPTION- allows them to grant or remove other users’ privileges

`GRANT type_of_permission ON database_name.table_name TO 'username'@'localhost';`

`REVOKE type_of_permission ON database_name.table_name FROM 'username'@'localhost';`

`SHOW GRANTS FOR 'username'@'localhost';`

`DROP USER 'username'@'localhost';`
* * *

/ ***Etel Sverdlov***  - https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql