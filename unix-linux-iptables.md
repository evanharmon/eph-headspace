# IPTABLES

## List Chains
`$ sudo iptables -L --line-numbers`

## List Rules
`$ iptables`

## List all rules of all tables
`$ iptables -L`

## Display rules for a specific tables
`$ iptables -L -t nat`

## List rules with line numbers
`$ iptables -L -n --line-numbers`

## Port Forwarding
```
$ iptables \
  -t nat \
  -A PREROUTING \
  -i eth0 \
  -p tcp \
  --dport $srcPortNumber \
  -j REDIRECT \
  --to-port $dstPortNumber
```

## Redirect
Used for redirecting local packets between services on the localhost

## DNAT
Alters packets destined outside of localhost

## Create a Chain
`$ iptables -N new_chain`

## Edit a chain
`$ iptables -E new_chain old_chain`

## Delete a chain
`$ iptables -X old_chain`

## List PREROUTING rules
`$ iptables -L -t nat --line-numbers`

## Port Forwarding
### Remember to do output as well bc the loopback interface isn't affected by PREROUTING
`$ iptables -t nat -A PREROUTING -p tcp --dport 80 -j REDIRECT --to-ports 9191`
`$ iptables -t nat -A OUTPUT -p tcp -o lo --dport 80 -j REDIRECT --to-ports 9191`

## Delete Prerouting Rule
`$ iptables -t nat -D PREROUTING 1`
