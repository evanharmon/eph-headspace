# DOCKER SECRETS

## Requirement: Start docker swarm / stack
`docker stack deploy -c docker-compose.yml mystack`

## Create a Docker Secret
`echo "evanharmon" | docker secret create github-user -`
