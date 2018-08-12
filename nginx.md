# NGINX

## Commands
stop, quit, reload, or reopen
`$ nginx -s {command}`

## Start
`$ sudo nginx`

## Mac Location
`/usr/local/etc/nginx`

## Linux Location
`/etc/nginx`

## Permissions issues
Mac - not sure how secure this is
`$ sudo chmod -R 777 /usr/local/var/run`

## Show Nginx and Config
`$ nginx -V`

## Redirect HTTPS to HTTP
Edit nginx.conf
```
upstream localhost {
  server localhost:3000;
}
```

## Nginx Server
```
server {
  listen       localhost:8081 ssl;
  server_name  localhost;

  access_log  /usr/local/var/log/nginx/sslredirect.access.log;
  error_log  /usr/local/var/log/nginx/sslredirect.error.log;

  ssl_certificate      /etc/nginx/ssl/my-server.crt.pem;
  ssl_certificate_key  /etc/nginx/ssl/my-server.key.pem;

  ssl_session_cache    shared:SSL:1m;
  ssl_session_timeout  5m;

  ssl_ciphers  HIGH:!aNULL:!MD5;
  ssl_prefer_server_ciphers  on;

  location / {
    proxy_read_timeout 150;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host:$server_port;
    proxy_set_header X-NginX-Proxy true;

    proxy_http_version 1.1;
    proxy_pass http://localhost/;
    #proxy_redirect http://localhost/ /;
    #proxy_redirect off;
  }
}
```

## Create Servers folder and server config
```
upstream localhost {
  server localhost:3000;
}
```

## Nginx Server
```
server {
  listen       localhost:8081 ssl;
  server_name  localhost;

  access_log  /usr/local/var/log/nginx/sslredirect.access.log;
  error_log  /usr/local/var/log/nginx/sslredirect.error.log;

  ssl_certificate      /etc/nginx/ssl/my-server.crt.pem;
  ssl_certificate_key  /etc/nginx/ssl/my-server.key.pem;

  ssl_session_cache    shared:SSL:1m;
  ssl_session_timeout  5m;

  ssl_ciphers  HIGH:!aNULL:!MD5;
  ssl_prefer_server_ciphers  on;

  location / {
    proxy_read_timeout 150;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host:$server_port;
    proxy_set_header X-NginX-Proxy true;

    proxy_http_version 1.1;
    proxy_pass http://localhost/;
    #proxy_redirect http://localhost/ /;
    #proxy_redirect off;
  }
}
```

## Create / Place SSL Certs
`/etc/nginx/ssl/my-server.crt.pem`
`/etc/nginx/ssl/my-server.key.pem`
