# HTPASSWD

## Create New Password File
enter sudo password for prompt
then type in new password, and confirm
```console
$ sudo htpasswd -c /etc/apache2/.htpasswd MyAdminUser
```
## Update Password File For User
enter sudo password for prompt
then type in new password, and confirm
```console
$ sudo htpasswd /etc/apache2/.htpasswd MyAdminUser
```

## Use In An NGINX Location Block
```
location /mylocation/ {
  auth_basic "My Service With Auth";
  auth_basic_user_file /etc/apache2/.htpasswd;
}
```
