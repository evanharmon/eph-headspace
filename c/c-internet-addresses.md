# C INTERNET ADDRESSES
IPV4

## in_addr
used just to hold netid/hostid 32-bit IP address in Network Byte Order
```
struct in_addr {
   unsigned long s_addr;
};
```

## Convert Internet String To Network Address
store in struct
returns 1 if valid, 0 for error
```
int inet_aton(const char *strptr, struct in_addr *addrptr)
   int retval;
   struct in_addr addrptr

   memset(&addrptr, '\0', sizeof(addrptr));
   retval = inet_aton("68.178.157.132", &addrptr);
```

## Convert Internet String To Integer
for network address
returns 32-bit network byte order ipv4 address, or INADDR_NONE on error
```
in_addr_t inet_addr(const char *strptr)
   struct sockaddr_in dest;

   memset(&dest, '\0', sizeof(dest));
   dest.sin_addr.s_addr = inet_addr("68.178.157.132");
```

## Convert Internet Host Address To Internet String
dot notation
```
char *inet_ntoa(struct in_addr inaddr)
   char *ip;

   ip = inet_ntoa(dest.sin_addr);

   printf("IP Address is: %s\n",ip);
```
