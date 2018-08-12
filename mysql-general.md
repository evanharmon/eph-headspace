# MYSQL

# Log In as Root
`$ mysql -u root us`

# CLI Change Root Password
`$ mysqladmin -u root -pcurrentpassword password 'newpassword'`

# Query Change Root Password
```
use mysql;
UPDATE user SET password=PASSWORD('newpassword') WHERE user='root';
```

# Check Connections as Admin
`$ show processlist;`

# Kill Connections as Admin

# Copy A Database <name>
```
$ mysqldump -u root <database_local> > dump.sql
$ mysqladmin -u root create <new_database_name>
$ mysql -u root <new_database_name> < dump.sql
```
