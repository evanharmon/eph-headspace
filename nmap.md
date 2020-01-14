# NMAP

## Summary

Notes on using the nmap cli tool

## Resources

- [Common Scan Commands](https://www.cyberciti.biz/tips/linux-scanning-network-for-open-ports.html)

## Install Mac OS X

```console
brew install nmap
```

## Scan Services Ports

```console
nmap -sO 10.10.100.254
```

## Scan TCP Ports

```console
nmap -PS 10.10.100.254
```

## Scan UDP Ports

```console
nmap -sU 10.10.100.254
```
