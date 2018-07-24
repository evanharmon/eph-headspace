## TCPFLOW
[Repo](https://github.com/simsong/tcpflow)

## Install
```
$ sudo bash yum -y install \
    git make gcc-c++ automake autoconf boost-devel cairo-devel libpcap-devel \
    openssl-devel zlib-devel
```
git clone and follow repo instructions

## Show Headers of Request Traffic
```
$ tcpflow -p -c -i eth0 port 80 |\
    grep -oE '(GET|POST|HEAD) .* HTTP/1.[01]|Host: .*'
```

## Show Cookie of Request Traffic
`$ tcpflow -c -p -i eth0 port 4984 | grep -oE '.*cookie:(.*)'`
