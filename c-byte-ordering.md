# C BYTE ORDERING

## sockaddr_in byte orders
sin_port and sin_addr members must have Network Byte Order designated

## Little Endian
low-order byte stored at addr (A), high-order byte stored on next addr (A + 1)

## Big Endian
high-order by stored at addr (A), low-order byte stored on next addr (A + 1)

## htons()
Host to Network Short
Converts 16 bit (2 bytes) from host byte order to network byte order

## htonl()
Host to Network Long
Converts 32 bit from host byte order to network byte order

## ntohl()
Network to Host Long
Converts 32 bit from network byte order to host byte order

## ntohs()
Network to Host Short
Converts 16 bit from network byte order to host byte order
