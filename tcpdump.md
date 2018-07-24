# TCPDUMP
[Guide](https://danielmiessler.com/study/tcpdump/)

## Raw Output view
`$ tcpdump -ttttnnvvS`

## Examine request headers
```
$ tcpdump -A \
  -s 0 'tcp port 80 and (((ip[2:2] - ((ip[0]&0xf)<<2)) - ((tcp[12]&0xf0)>>2)) != 0)'
```
## Examine response headers
```
$ tcpdump -X \
  -s 0 'tcp port 80 and (((ip[2:2] - ((ip[0]&0xf)<<2)) - ((tcp[12]&0xf0)>>2)) != 0)'
```
