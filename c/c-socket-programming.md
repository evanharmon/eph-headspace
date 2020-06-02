# C SOCKET PROGRAMMING
(http://www.cs.rpi.edu/~moorthy/Courses/os98/Pgms/socket.html)
(http://www.tutorialspoint.com/unix_sockets/socket_structures.htm)

## Sockaddr
holds socket family and data
```
struct sockaddr {
   unsigned short   sa_family;
   char             sa_data[14];
};
```

## Sockaddr_in
used to references sockets elements
```
struct sockaddr_in {
   short int            sin_family;
   unsigned short int   sin_port;
   struct in_addr       sin_addr;
   unsigned char        sin_zero[8];
};
sin_zero = NULL # always set to Null, not used
```

## Socket Example
```
#include <stdio.h>
#include <stdlib.h>
#include <sys/socket.h>
#include <netinet/in.h>

int
make_socket ( uint16_t port)
{
  int sock;
  struct sockaddr_in name;

  /* Create the socket. */
  sock = socket (PF_INET, SOCK_STREAM, 0);
  if (sock < 0) {
    perror ("socket");
    exit (EXIT_FAILURE);
  }

  /* Give the socket a name. */
  name.sin_family = AF_INET;
  name.sin_port = htons (port);
  name.sin_addr.s_addr = htonl (INADDR_ANY);
  if (bind (sock, (struct sockaddr *) &name, sizeof (name)) < 0) {
    perror ("bind");
    exit (EXIT_FAILURE);
  }

  return sock;
}
```

## Connect
returns -1 on error
serv_addr is pointer to sockaddr with IP/port
`int connect(int sockfd, struct sockaddr *serv_addr, int addrlen)`

## Send
send data over connected datagram sockets
set flags to 0
`int send(int sockfd, const void *msg, int len, int flags)`

## Receive
receive data over connected datagram sockets
flags set to 0
`int recv(int sockfd, void *buf, int len, unsigned int flags)`

## Close
immediate close
`int close(int sockfd)`

## Shutdown
Graceful close
how: 0 - recv not allowed, 1 sending not allowed, 2 same as close()
`int shutdown(int sockfd, int how)`

-------------------
## Select
- non-blocking, indicates which fd is ready for reading/writing or has error
- nfds - range of file descriptors to test
- readfds, writefds, errorfds can be NULL
- if timeout is 0, will return immediately
- if timeout is NULL, will block until one fds ready

```
int select(int nfds, fd_set *readfds, fd_set, *writefds, fd_set *errorfds, struct timeval *timeout)
```

behavior of below macros is undefined if fd argument < 0 or >= FD_SETSIZE
clears the bit for fd
`FD_CLR(fd, &fdset)`

check if set
`FD_ISSET(fd, &fdset)`

sets the bit for fd
`FD_SET(fd, &fdset)`

initialize fdset
```
FD_ZERO(&fdset)

fd_set fds;

struct timeval tv;

/* do socket initialization etc.
tv.tv_sec = 1;
tv.tv_usec = 500000;

/* tv now represents 1.5 seconds */
FD_ZERO(&fds);

/* adds sock to the file descriptor set */
FD_SET(sock, &fds);

/* wait 1.5 seconds for any data to be read from any single socket */
select(sock+1, &fds, NULL, NULL, &tv);

if (FD_ISSET(sock, &fds)) {
   recvfrom(s, buffer, buffer_len, 0, &sa, &sa_len);
   /* do something */
}
else {
   /* do something else */
}
```

## Pass To Functions
pass the pointer, and size of struct
called value/result argument
`bzero((char *) &serv_addr, sizeof(serv_addr));`

## Set Struct Vars To Null "\0"
use memset() for bzero()
avoids junk values in struct
