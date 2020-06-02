# C SERVER HOSTS

## Servent
contains info for server and associated ports
```
struct servent {
   char  *s_name;
   char  **s_aliases;
   int   s_port;
   char  *s_proto;

};
s_name # name of service, FTP, SMTP, POP3, etc
s_aliases = NULL # list of service aliases, usually NULL
s_port # port
s_proto # protocol, TCP or UDP
```

## Servent Port Number
returns service port #
`*getservbyname(char *name, char *proto)`

## Servent Service Name
returns service name
`*getservbyport(int port, char *proto)`

## Bind - Server Only
returns -1 on error
```
int bind(int sockfd, struct sockaddr *my_addr, int addrlen)
sever.sin_port = 0; # random port
server.sin_addr.s_addr = INADDR_ANY; # auto assign
```

## Listen - Server Only
converts unconnected socket into passive socket
backlog is # max number of connections
`int listen(int sockfd, int backlog)`

## Accept - Server Only
cliaddr is client address/port
`int accept(int sockfd, struct sockaddr *cliaddr, socklen_t *addrlen)`

## Hostent
contains info for host
```
struct hostent {
   char *h_name;
   char **h_aliases;
   int h_addrtype;
   int h_length;
   char **h_addr_list

#define h_addr  h_addr_list[0]

};
h_name # hostname
h_aliases # host name aliases
h_addrtype = AF_INET
h_length = 4 # length of ip address
h_addr_list # array of pointers of addresses
```
