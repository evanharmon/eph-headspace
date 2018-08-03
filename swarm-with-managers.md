# DOCKER SWARM HANDLING MANAGERS
From Jay Johnson

1) Join the primary as a worker:
```
root@ce-manager3:~# docker swarm join \
  --listen-addr 163.172.82.128:2377 \
  --token abcd 163.172.58.92:2377
```

2) Promote the new host to be a manager from a manager host:
`root@ce-manager1:~# docker node promote abcd`

or in one command:
```
$ newmanager=ce-manager3 &&\
  docker node promote \
  $(docker node ls | grep ${newmanager} | grep Ready | awk '{print $1}') &&\
  docker node update --availability drain \
  $(docker node ls | grep ${newmanager} | grep Ready | awk '{print $1}')
```

3) Confirm the new host is a manager:

4) Demote the manager from the swarm:
`root@ce-manager1:~# docker node demote xyz`
