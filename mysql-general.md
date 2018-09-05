# MYSQL

## Default Port
3306

## Log In As Root
```console
$ mysql -u root us
```

## CLI Change Root Password
```console
$ mysqladmin -u root -pcurrentpassword password 'newpassword'
```

## Query Change Root Password
```
use mysql;
UPDATE user SET password=PASSWORD('newpassword') WHERE user='root';
```

## Check Connections As Admin
```console
$ show processlist;
```

## Kill Connections As Admin

## Copy A Database <name>
```console
$ mysqldump -u root <database_local> > dump.sql
$ mysqladmin -u root create <new_database_name>
$ mysql -u root <new_database_name> < dump.sql
```
